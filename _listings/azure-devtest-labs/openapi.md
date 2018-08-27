---
swagger: "2.0"
x-collection-name: Azure DevTest Labs
x-complete: 1
info:
  title: DevTestLabsClient
  description: the-devtest-labs-client-
  version: 1.0.0
host: management.azure.com
basePath: /
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  ? /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.DevTestLab/labs/{labName}/users/{userName}/disks
  : get:
      summary: Disks List
      description: List disks in a given user profile.
      operationId: Disks_List
      x-api-path-slug: subscriptionssubscriptionidresourcegroupsresourcegroupnameprovidersmicrosoft-devtestlablabslabnameusersusernamedisks-get
      parameters:
      - in: query
        name: $expand
        description: Specify the $expand query
      - in: query
        name: $filter
        description: The filter to apply to the operation
      - in: query
        name: $orderby
        description: The ordering expression for the results, using OData notation
      - in: query
        name: $top
        description: The maximum number of resources to return from the operation
      - in: path
        name: labName
        description: The name of the lab
      - in: query
        name: No Name
      - in: path
        name: userName
        description: The name of the user profile
      responses:
        200:
          description: OK
      tags:
      - Disks
  ? /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.DevTestLab/labs/{labName}/users/{userName}/disks/{name}
  : get:
      summary: Disks Get
      description: Get disk.
      operationId: Disks_Get
      x-api-path-slug: subscriptionssubscriptionidresourcegroupsresourcegroupnameprovidersmicrosoft-devtestlablabslabnameusersusernamedisksname-get
      parameters:
      - in: query
        name: $expand
        description: Specify the $expand query
      - in: path
        name: labName
        description: The name of the lab
      - in: path
        name: name
        description: The name of the disk
      - in: query
        name: No Name
      - in: path
        name: userName
        description: The name of the user profile
      responses:
        200:
          description: OK
      tags:
      - Disks
    put:
      summary: Disks Create Or Update
      description: Create or replace an existing disk. This operation can take a while
        to complete.
      operationId: Disks_CreateOrUpdate
      x-api-path-slug: subscriptionssubscriptionidresourcegroupsresourcegroupnameprovidersmicrosoft-devtestlablabslabnameusersusernamedisksname-put
      parameters:
      - in: body
        name: disk
        description: A Disk
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: labName
        description: The name of the lab
      - in: path
        name: name
        description: The name of the disk
      - in: query
        name: No Name
      - in: path
        name: userName
        description: The name of the user profile
      responses:
        200:
          description: OK
      tags:
      - Disks
    delete:
      summary: Disks Delete
      description: Delete disk. This operation can take a while to complete.
      operationId: Disks_Delete
      x-api-path-slug: subscriptionssubscriptionidresourcegroupsresourcegroupnameprovidersmicrosoft-devtestlablabslabnameusersusernamedisksname-delete
      parameters:
      - in: path
        name: labName
        description: The name of the lab
      - in: path
        name: name
        description: The name of the disk
      - in: query
        name: No Name
      - in: path
        name: userName
        description: The name of the user profile
      responses:
        200:
          description: OK
      tags:
      - Disks
  ? /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.DevTestLab/labs/{labName}/users/{userName}/disks/{name}/attach
  : post:
      summary: Disks Attach
      description: Attach and create the lease of the disk to the virtual machine.
        This operation can take a while to complete.
      operationId: Disks_Attach
      x-api-path-slug: subscriptionssubscriptionidresourcegroupsresourcegroupnameprovidersmicrosoft-devtestlablabslabnameusersusernamedisksnameattach-post
      parameters:
      - in: body
        name: attachDiskProperties
        description: Properties of the disk to attach
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: labName
        description: The name of the lab
      - in: path
        name: name
        description: The name of the disk
      - in: query
        name: No Name
      - in: path
        name: userName
        description: The name of the user profile
      responses:
        200:
          description: OK
      tags:
      - Disks
  ? /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.DevTestLab/labs/{labName}/users/{userName}/disks/{name}/detach
  : post:
      summary: Disks Detach
      description: Detach and break the lease of the disk attached to the virtual
        machine. This operation can take a while to complete.
      operationId: Disks_Detach
      x-api-path-slug: subscriptionssubscriptionidresourcegroupsresourcegroupnameprovidersmicrosoft-devtestlablabslabnameusersusernamedisksnamedetach-post
      parameters:
      - in: body
        name: detachDiskProperties
        description: Properties of the disk to detach
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: labName
        description: The name of the lab
      - in: path
        name: name
        description: The name of the disk
      - in: query
        name: No Name
      - in: path
        name: userName
        description: The name of the user profile
      responses:
        200:
          description: OK
      tags:
      - Disks
---