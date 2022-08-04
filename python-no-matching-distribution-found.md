# Python No matching distribution found for <package>

## Background
This can happen when trying to install a pip package that hasn't been built for your system. 

Pip and python use 'wheel files' which are essentially weird tarballs. They are matched to
an operating system and archiecture. If there is no published wheel file that matches your
set-up, you'll get this message.

## Fix

pip has a `-e` flag that allows you to install a dependency via a local folder. So instead
of using wheel files published on pypi you can use a git repo on your machine instead.

This lets you basically build from source instead of relying on the package maintainer
publishing something tidy for your system.

## Example 

I wanted to install `rusty-rlp` but it is unsupported on arm64 architectures.

Solution:

`git clone https://github.com/cburgdorf/rusty-rlp`
`pip install -e ./rusty-rlp`
