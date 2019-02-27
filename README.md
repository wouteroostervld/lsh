# lsh

Literal shellscript: document and execute shellcode in your markdown.

## Purpose

Wouldn't it be nice to have your examples in markdown to be directly
executable? Now you can.

Inspired by literal haskell.

## Example

Just mix your shellscript with mardown like this:

    if ! which cowsay >/dev/null; then
      if which yum >/dev/null; then
        sudo yum -y install cowsay
      fi
      if which apt-get >/dev/null; then
        sudo apt-get update
        sudo apt-get -y install cowsay
      fi
      if which pkg >/dev/null; then
        sudo pkg install -y cowsay
      fi
    fi
    #$WHAT: something say to about this
    : ${WHAT:=awesome}
    cowsay "This is $WHAT!"
    exit

Run this markdown like this:

    bin/lsh -x README.md

## Default action

Dump script:

    bin/lsh README.md

## Edit

    bin/lsh -e README.md

## Edit and execute

    bin/lsh -ex README.md
