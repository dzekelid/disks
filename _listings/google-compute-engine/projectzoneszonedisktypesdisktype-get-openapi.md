---
swagger: "2.0"
x-collection-name: Google Compute Engine
x-complete: 0
info:
  title: Google Compute Engine API Get Zone Disk Type
  description: Returns the specified disk type. Get a list of available disk types
    by making a list() request.
  contact:
    name: Google
    url: https://google.com
  version: v1
host: www.googleapis.com
basePath: /compute/v1/projects
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /{project}/aggregated/diskTypes:
    get:
      summary: Get Disk Type
      description: Retrieves an aggregated list of disk types.
      operationId: compute.diskTypes.aggregatedList
      x-api-path-slug: projectaggregateddisktypes-get
      parameters:
      - in: query
        name: filter
        description: Sets a filter expression for filtering listed resources, in the
          form filter={expression}
      - in: query
        name: maxResults
        description: The maximum number of results per page that should be returned
      - in: query
        name: orderBy
        description: Sorts list results by a certain order
      - in: query
        name: pageToken
        description: Specifies a page token to use
      - in: path
        name: project
        description: Project ID for this request
      responses:
        200:
          description: OK
      tags:
      - Disk
      - Aggregation
  /{project}/aggregated/disks:
    get:
      summary: Get Disks
      description: Retrieves an aggregated list of persistent disks.
      operationId: compute.disks.aggregatedList
      x-api-path-slug: projectaggregateddisks-get
      parameters:
      - in: query
        name: filter
        description: Sets a filter expression for filtering listed resources, in the
          form filter={expression}
      - in: query
        name: maxResults
        description: The maximum number of results per page that should be returned
      - in: query
        name: orderBy
        description: Sorts list results by a certain order
      - in: query
        name: pageToken
        description: Specifies a page token to use
      - in: path
        name: project
        description: Project ID for this request
      responses:
        200:
          description: OK
      tags:
      - Disk
      - Aggregation
  /{project}/moveDisk:
    post:
      summary: Move Disk
      description: Moves a persistent disk from one zone to another.
      operationId: compute.projects.moveDisk
      x-api-path-slug: projectmovedisk-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: project
        description: Project ID for this request
      responses:
        200:
          description: OK
      tags:
      - Disk
  /{project}/zones/{zone}/diskTypes:
    get:
      summary: Get Zone Disk Types
      description: Retrieves a list of disk types available to the specified project.
      operationId: compute.diskTypes.list
      x-api-path-slug: projectzoneszonedisktypes-get
      parameters:
      - in: query
        name: filter
        description: Sets a filter expression for filtering listed resources, in the
          form filter={expression}
      - in: query
        name: maxResults
        description: The maximum number of results per page that should be returned
      - in: query
        name: orderBy
        description: Sorts list results by a certain order
      - in: query
        name: pageToken
        description: Specifies a page token to use
      - in: path
        name: project
        description: Project ID for this request
      - in: path
        name: zone
        description: The name of the zone for this request
      responses:
        200:
          description: OK
      tags:
      - Disk
  /{project}/zones/{zone}/diskTypes/{diskType}:
    get:
      summary: Get Zone Disk Type
      description: Returns the specified disk type. Get a list of available disk types
        by making a list() request.
      operationId: compute.diskTypes.get
      x-api-path-slug: projectzoneszonedisktypesdisktype-get
      parameters:
      - in: path
        name: diskType
        description: Name of the disk type to return
      - in: path
        name: project
        description: Project ID for this request
      - in: path
        name: zone
        description: The name of the zone for this request
      responses:
        200:
          description: OK
      tags:
      - Disk
  /{project}/zones/{zone}/disks:
    get:
      summary: Get Zone Disks
      description: Retrieves a list of persistent disks contained within the specified
        zone.
      operationId: compute.disks.list
      x-api-path-slug: projectzoneszonedisks-get
      parameters:
      - in: query
        name: filter
        description: Sets a filter expression for filtering listed resources, in the
          form filter={expression}
      - in: query
        name: maxResults
        description: The maximum number of results per page that should be returned
      - in: query
        name: orderBy
        description: Sorts list results by a certain order
      - in: query
        name: pageToken
        description: Specifies a page token to use
      - in: path
        name: project
        description: Project ID for this request
      - in: path
        name: zone
        description: The name of the zone for this request
      responses:
        200:
          description: OK
      tags:
      - Disk
    post:
      summary: Create Zone Disk
      description: Creates a persistent disk in the specified project using the data
        in the request. You can create a disk with a sourceImage, a sourceSnapshot,
        or create an empty 500 GB data disk by omitting all properties. You can also
        create a disk that is larger than the default size by specifying the sizeGb
        property.
      operationId: compute.disks.insert
      x-api-path-slug: projectzoneszonedisks-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: project
        description: Project ID for this request
      - in: query
        name: sourceImage
        description: Optional
      - in: path
        name: zone
        description: The name of the zone for this request
      responses:
        200:
          description: OK
      tags:
      - Disk
  /{project}/zones/{zone}/disks/{disk}:
    delete:
      summary: Delete Zone Disk
      description: Deletes the specified persistent disk. Deleting a disk removes
        its data permanently and is irreversible. However, deleting a disk does not
        delete any snapshots previously made from the disk. You must separately delete
        snapshots.
      operationId: compute.disks.delete
      x-api-path-slug: projectzoneszonedisksdisk-delete
      parameters:
      - in: path
        name: disk
        description: Name of the persistent disk to delete
      - in: path
        name: project
        description: Project ID for this request
      - in: path
        name: zone
        description: The name of the zone for this request
      responses:
        200:
          description: OK
      tags:
      - Disk
    get:
      summary: Get Zone Disk
      description: Returns a specified persistent disk. Get a list of available persistent
        disks by making a list() request.
      operationId: compute.disks.get
      x-api-path-slug: projectzoneszonedisksdisk-get
      parameters:
      - in: path
        name: disk
        description: Name of the persistent disk to return
      - in: path
        name: project
        description: Project ID for this request
      - in: path
        name: zone
        description: The name of the zone for this request
      responses:
        200:
          description: OK
      tags:
      - Disk
  /{project}/zones/{zone}/disks/{disk}/createSnapshot:
    post:
      summary: Create Snapshot of Zone Disk
      description: Creates a snapshot of a specified persistent disk.
      operationId: compute.disks.createSnapshot
      x-api-path-slug: projectzoneszonedisksdiskcreatesnapshot-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: disk
        description: Name of the persistent disk to snapshot
      - in: query
        name: guestFlush
      - in: path
        name: project
        description: Project ID for this request
      - in: path
        name: zone
        description: The name of the zone for this request
      responses:
        200:
          description: OK
      tags:
      - Disk
  /{project}/zones/{zone}/disks/{disk}/resize:
    post:
      summary: Resize Zone Disk
      description: Resizes the specified persistent disk.
      operationId: compute.disks.resize
      x-api-path-slug: projectzoneszonedisksdiskresize-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: disk
        description: The name of the persistent disk
      - in: path
        name: project
        description: Project ID for this request
      - in: path
        name: zone
        description: The name of the zone for this request
      responses:
        200:
          description: OK
      tags:
      - Disk
  /{project}/zones/{zone}/instances/{instance}/attachDisk:
    post:
      summary: Attach Disk to Zone Instance
      description: Attaches a Disk resource to an instance.
      operationId: compute.instances.attachDisk
      x-api-path-slug: projectzoneszoneinstancesinstanceattachdisk-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: instance
        description: The instance name for this request
      - in: path
        name: project
        description: Project ID for this request
      - in: path
        name: zone
        description: The name of the zone for this request
      responses:
        200:
          description: OK
      tags:
      - Disk
x-streamrank:
  polling_total_time_average: 0
  polling_size_download_average: 0
  streaming_total_time_average: 0
  streaming_size_download_average: 0
  change_yes: 0
  change_no: 0
  time_percentage: 0
  size_percentage: 0
  change_percentage: 0
  last_run: ""
  days_run: 0
  minute_run: 0
---