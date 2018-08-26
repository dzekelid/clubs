---
swagger: "2.0"
x-collection-name: Strava
x-complete: 1
info:
  title: Strava API v3
  description: strava-api
  version: 1.0.0
host: www.strava.com
basePath: /api/v3
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /athlete/clubs:
    get:
      summary: List Athlete Clubs
      description: Returns a list of the clubs whose membership includes the authenticated
        athlete.
      operationId: getLoggedInAthleteClubs
      x-api-path-slug: athleteclubs-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: Successful response
      tags:
      - Sports
      - List
      - Athlete
      - Clubs
  /clubs/{id}:
    get:
      summary: Get Club
      description: Returns a given club using its identifier.
      operationId: getClubById
      x-api-path-slug: clubsid-get
      parameters:
      - in: path
        name: id
        description: The identifier of the club
      responses:
        200:
          description: Successful response
      tags:
      - Sports
      - Club
  /clubs/{id}/members:
    get:
      summary: List Club Members
      description: Returns a list of the athletes who are members of a given club.
      operationId: getClubMembersById
      x-api-path-slug: clubsidmembers-get
      parameters:
      - in: path
        name: id
        description: The identifier of the club
      - in: query
        name: No Name
      responses:
        200:
          description: Successful response
      tags:
      - Sports
      - List
      - Club
      - Members
  /clubs/{id}/admins:
    get:
      summary: List Club Administrators.
      description: Returns a list of the administrators of a given club.
      operationId: getClubAdminsById
      x-api-path-slug: clubsidadmins-get
      parameters:
      - in: path
        name: id
        description: The identifier of the club
      - in: query
        name: No Name
      responses:
        200:
          description: Successful response
      tags:
      - Sports
      - List
      - Club
      - Administrators
  /clubs/{id}/activities:
    get:
      summary: List Club Activities
      description: Retrieve recent activities from members of a specific club. The
        authenticated athlete must belong to the requested club in order to hit this
        endpoint. Pagination is supported. Enhanced Privacy Mode is respected for
        all activities.
      operationId: getClubActivitiesById
      x-api-path-slug: clubsidactivities-get
      parameters:
      - in: path
        name: id
        description: The identifier of the club
      - in: query
        name: No Name
      responses:
        200:
          description: Successful response
      tags:
      - Sports
      - List
      - Club
      - Activities
  /clubs/{id}/join:
    post:
      summary: Join Club
      description: Adds the authenticated athlete to the club's membership.
      operationId: joinClubById
      x-api-path-slug: clubsidjoin-post
      parameters:
      - in: path
        name: id
        description: The identifier of the club
      responses:
        200:
          description: Successful response
      tags:
      - Sports
      - Join
      - Club
  /clubs/{id}/leave:
    post:
      summary: Leave Club
      description: Removes the authenticated athlete from the club's membership.
      operationId: leaveClubById
      x-api-path-slug: clubsidleave-post
      parameters:
      - in: path
        name: id
        description: The identifier of the club
      responses:
        200:
          description: Successful response
      tags:
      - Sports
      - Leave
      - Club
---