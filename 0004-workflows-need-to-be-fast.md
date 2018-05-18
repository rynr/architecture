# 4. Workflows need to be fast

Date: 2018-05-18

## Status

Accepted

## Context

Having a developer waiting for any process to finish is a stupid thing. It's not only that it's to long for the developer to wait, it also hinders you from fixing issues fast.

## Decision

Release processes need to be very fast and fully automated.

## Consequences

Any process happening with the code needs to be automated. The power of the machine working on should be used if the tests are running, so testing should be able to utilize multiple cores on a computer to get throug as fast as possible. The process should also be documented (see also [#3](./0003-have-the-master-documentation-in-the-readme.md)) and as easy that anybody can run them. It also should be possible for everybody to build and deploy a release.
