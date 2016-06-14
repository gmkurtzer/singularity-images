This is a repository for Singularity container base OS images. To include
images into this repository, please fork the repo and submit pull a pull
request making sure you abide by the following standards.

## The container nomenclature
Within the final directory defined above, the container nomenclature itself
must represent much of the above information in the following order:

1. The distribution name
2. Build specific nomenclature
3. Version string
4. Date build string in the format of YYYY-MM-DD (optional but encouraged)
5. Architecture
6. End with .img

### Examples

```
centos-base-7.2-2016-05-01.x86_64.img
scientific-python-6.5.x86_64.img
```


## Directory structure
The directory structure is all in lowercase and each directory into the
path is defined as follows:

1. The distribution name (e.g. centos, redhat, ubuntu, mint, etc.)
2. Version string as defined by the distribution (e.g. 7.1)
3. Architecture (e.g. x86_64/amd64, i386, ppc, etc.)
4. Build specific nomenclature (e.g. base, python, R, base_mpi, etc.)

### Examples

```
centos/7.2/x86_64/base/
redhat/5.0/i386/python
```


# Container inclusion standards
Within the directory defined above, do the following:

* Provide the bootstrap definition that created the container and use
the name `BOOTSTRAP.def`
* Create a tar archive of the container itself
(`tar -CjSf $full_container_name.tbz2 $full_container_name`)
* Include a `MAINTAINER` file (template below)
* Include a `DESCRIPTION` file (template below)


## Maintainer file
In the container directory, you must include a MAINTAINER file which
includes the following information:

```
NAME: Your Name
EMAIL: Your@Email
GITHUB: https://github.com/username
```


## Description file
In the container direcotry you must include a DESCRIPTION file which
includes the following information:

```
DISTRIBUTION: distribution_name
VERSION: distribution_version
ARCHITECTURE: distribution_architecture
TARBALLSUM: md5sum_checksum_of_tarball (NOT IMAGE!)
DATE: YYYY-MM-DD

Here you will provide a free form summary about the container, any specific
features you have included, motivation, etc.

```


