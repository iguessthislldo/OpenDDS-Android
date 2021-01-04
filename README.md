# An ACE/TAO/OpenDDS Build Matrix for Android  [![matrix](https://github.com/iguessthislldo/OpenDDS-Android/workflows/matrix/badge.svg)](https://github.com/iguessthislldo/OpenDDS-Android/actions?query=workflow%3Amatrix)

Scripts for building [OpenDDS](https://github.com/objectcomputing/OpenDDS)
against various combinations of Android NDK and API versions on GitHub Actions.

## Matrix

<!-- BEGIN MATRIX -->
<!-- This part is generated by matrix.py -->
`M` = [`doc_group_master`](https://github.com/DOCGroup/ACE_TAO)
`6` = [`doc_group_ace6_tao2`](https://github.com/DOCGroup/ACE_TAO/tree/ace6tao2)
`O` = [`oci`](https://theaceorb.com/)
|  | 16 | 17 | 18 | 19 | 21 | 22 | 23 | 24 | 26 | 27 | 28 | 29 | 30 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| r22 | `M`,`6`,`O` | `M`,`6`,`O` | `M`,`6`,`O` | `M`,`6`,`O` | `M`,`6`,`O` | `M`,`6`,`O` | `M`,`6`,`O` | `M`,`6`,`O` | `M`,`6`,`O` | `M`,`6`,`O` | `M`,`6`,`O` | `M`,`6`,`O` | `M`,`6`,`O` |
| r21d | `M` | - | - | - | - | - | - | - | - | - | - | `M` | - |
| r20b | `M` | - | - | - | - | - | - | - | - | - | - | `M` | - |
| r19c | `M`,`6` | - | - | - | - | - | - | - | - | - | `M`,`6` | - | - |
| r18b | `M`,`6` | - | - | - | - | - | - | - | - | - | `M`,`6` | - | - |
| r12b | `6` | - | - | - | - | - | - | `6` | - | - | - | - | - |
<!-- END MATRIX -->

### Modifying the Matrix

To change the matrix, edit `matrix.py` and run the script with Python 3. It
will update `.github/workflows/matrix.yml` and `README.md` (this file).

## Running Locally

There used to be a shell version of the matrix but I never used it beyond
initial testing so eventually I removed it. These instructions are for doing a
single build. These are bash scripts developed on a Ubuntu Linux system. They
might need some modifications to work on other Linux systems or macOS.

1. Copy `default.settings.sh` to `settings.sh` and modify it as you see fit.
   You can also set the environment variables in this file instead. See next
   section about that.
2. Run `run.sh`.

That's it, assuming nothing goes wrong. Doing multiple builds in a row will
require some cleanup.

## Environment Variables

There are several environment variables that are the normal settings for the
build. These all can be found in `default.settings.sh`. The first three: `ndk`,
`arch`, and `api` are required so set to some example values. The rest are
optional.

In addition to those, what ACE/TAO and OpenDDS it clones can optionally be
controlled using `ACE_TAO_REPO`, `ACE_TAO_BRANCH`, `OPENDDS_REPO`, and
`OPENDDS_BRANCH`.

## Legal

By running this you are implicitly agreeing to the licences for the Android SDK
and the Android NDK, as well as OpenDDS, ACE/TAO, as well as anything else.
