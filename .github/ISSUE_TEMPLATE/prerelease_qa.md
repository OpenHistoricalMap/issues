---
name: Prelease QA Pass
about: Checklist to validate key functionality before release
title: 'Prelease QA Pass'
labels: 'infrastructure'
assignees: ''

---

## Website
- [ ] User creation
- [ ] User Login in website
- [ ] Check all the important URLs route on the site, navigating between them and confirming that login is respected
- [ ] Verify that all tabs in the main page load correctly
    - History
      - [ ] Displays a list of changesets
    - Export
      - [ ] Zooming out triggers an _area is too large__ warning
      - [ ] __Export__ generates a __map.osm__ file for download 
    - GPS Traces (does not work locally)
      - Verify that a new __Identifiable__ trace can be uploaded
      - [ ] File uploads without error
      - [ ] Trace is marked as pending in table row
      - [ ] Email is generated & sent when processed
      - [ ] Trace outline is displayed in table row with displayname, number of points, __IDENTIFIABLE__ badge, elapsed time since posting, display name, and description
      - [ ] __View Map__ plots a marker at correct location
    - User Diaries
      - [ ] Displays a list of __Recent diary entries__
    - Copyright
      - [ ] Displays the __Copyright and License__ page with no errors or irrelevant (e.g., suspicious OSM/upstream) strings.
    - Help
      - [ ] Displays the __Getting Help__ page with carded options. 
    - About
      - [ ] Displays a noticeably styled page with no errors or irrelevant (e.g., suspicious OSM/upstream) strings.
- [ ] Verify that all dropdowns for __displayname__ work correctly
  - My Dashboard
    - [ ] Displays potential lists of friends and other nearby users
  - My Messages
    - [ ] Displays message count in dropdown, new, old, & sent on page
  - My Profile
    - [ ] Displays profiel picture, stats, __Edit__ option 
  - My Settings
    - [ ] Displays tabs for Settings, auth applications, and auth authorizations
  - My Preferences
    - [ ] Displays editor and language preferences
- [ ] Verify that enhanced inspector is loading. This way should load a slideshow with photos. If it does not, that usually means we need to adjust our injection code to target changed HTML in the upstream code.
    - [staging](https://staging.openhistoricalmap.org/way/198636092#map=20/37.90452/-122.55273&layers=OD&date=1923-01-01&daterange=1923-01-01,2023-12-31)
    - [production](https://www.openhistoricalmap.org/way/198636092#map=20/37.90452/-122.55273&layers=OD&date=1923-01-01&daterange=1923-01-01,2023-12-31)
- [ ] Search for a location using the search bar
- [ ] User logout

## iD

 - [ ] __Edit__, __Update__, and __Remove__ each type of object: node, way, relations in dates `start_date=1800`  and `end_date=2023` and make sure to add a name `name=<uniq>`, because name is going to be used to test in nominatim
        - Make an edit with something we know is symbolized clearly on the map
        - Examples: Landuse, Buildings, highways, POI
    - [ ] Upload changesets
    - [ ] View the changeset and note if session persists

## JOSM
- Check authentication
  - [ ] Should be possible to login using OAuth 2
  - [ ] Should be impossible to login using OAuth 1 or Basic Auth
- [ ]  Edit in JOSM and confirm we can push to right place: staging or production
     - https://staging.openhistoricalmap.org/api
     - https://www.openhistoricalmap.org/api
- [ ] Make some random edits with range of date
- [ ] Upload changesets

## Minute replication reflects the changesets
- [ ] http://planet.openhistoricalmap.org/
- [ ] http://planet-staging.openhistoricalmap.org/

## Tiler
- [ ] Confirm that the edit is appearing in the vector tiles in a timely manner (10 min)
- [ ] Play with the range dates in the website, according the `start_date` and `end_date` tags of the features.

## Nominatim
- [ ] Test searches on Nominatim, for a known working thing. 
- [ ] Add something new to OHM that Nominatim will search, then confirm it is searchable
   - https://nominatim-staging.openhistoricalmap.org/
   - https://nominatim.openhistoricalmap.org/

## OSMCha
- Check authentication
  - [ ] Should be possible to login using OAuth 2
  - [ ] Should be impossible to login using OAuth 1 or Basic Auth

## Overpass
 - [ ] Use overpass turbo to query Overpass to confirm that new edits are showing up
   - https://overpass-turbo-staging.openhistoricalmap.org/
   - https://overpass-turbo.openhistoricalmap.org/
    
## Taginfo

Note: taginfo has been updating every week, so it may not be necessary to test.

- [ ] Confirm TagInfo is consuming and updating diffs
    - https://taginfo-staging.openhistoricalmap.org/keys
    - https://taginfo.openhistoricalmap.org/keys

## Tasking Manager
- Check authentication
  - [ ] Should be possible to login using OAuth 2
  - [ ] Should be impossible to login using OAuth 1 or Basic Auth
