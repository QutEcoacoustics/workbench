# Functional specifications

The Acoustic Workbench is a web application that allows users to manage and
analyze ecoacoustics data.

The following specifications are in various states of completion and availability.

## User

A user should be able to:

- create, edit, and delete an _account_
- create and manage _projects_ to logically organize their data
  - manage access to their _projects_ by other _users_, including whether or not their _projects_ are public
  - manage whether or not users are allowed to download original _audio recordings_ from their _projects_
  - create a citation for their project
  - choose a license for their project
  - create a DOI for their project
- create and manage _sites_ (a collection of _points_ roughly geographically co-located) inside _projects_
- create and manage _points_ within _sites_
  - a _point_ is the location where _audio recordings_ were created by a _device_
- upload _audio recordings_ to _points_
- download _audio recordings_ from any _projects_ they have access to
- listen to _audio recordings_ they have access to
- visualize _audio recordings_ they have access to
- annotate _audio recordings_ they have access to
- access a library of example _annotations_
- download _annotations_ from any _audio recordings_ they have access to
- upload _annotations_ to _audio recordings_ they have access to
  - Sometimes analysis is done offline and the results are uploaded to the workbench
- validate sets of _annotations_ to ensure they are correct
- download _analysis results_ that are generated from _audio recordings_ they have access to
- create and manage their own _analysis jobs_ to run on _audio recordings_ they have access to
  - and view the _analysis results_ of their _analysis jobs_
- search through all _audio recordings_ they have access to through the submission of a sample file (similarity search)
- generate reports that detail the _annotations_ and _analysis results_ of _audio recordings_ they have access to

## System

The system should:

- be vendor independent
  - As in it should not be dependent on any hardware or software that cannot be setup or moved to another location or vendor
    - e.g. We should not use cloud specific APIs
    - e.g. Being tied to one specific operating system
- be runnable locally in a development environment
- be runnable on Linux
- be containerized
- be wholly exposed through a RESTful API
- have a front end web interface
- have a thorough set of automated tests
- support the storage of large sets of audio data
  - this includes ingestion (and repair) of audio data
  - this includes downloading data
- support the storage of large sets of analysis results
- should be able to serve media to users in a variety of formats and sizes
  - e.g. segmentation and format conversion ideal for display segments in a web browser
- be able to support massive parallelization of analysis jobs
  - We currently assume we have access to a PBS cluster via SSH
  