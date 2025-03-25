---
name: Tasking-Manager Pre-Release QA Pass
about: Checklist to validate tasking-manager functionality before release
title: 'TM Pre-Release QA Pass'
labels: 'infrastructure'
assignees: ''

---

## OHM Tasking-Manager testing
- main page
  - [ ] Sign up by creation an account in OHM
  - [ ] User login
  - [ ] Verify that stats load correctly
  - Verify that all tabs in the main page load correctly:
    - [ ] Explore Projects
    - [ ] My Contributions: hidden for non-logged in users
    - [ ] Learn
    - [ ] About
  - [ ] Verify that all links are working correctly
  - [ ] Verify that OHM links route to OHM entities
  - [ ] Verify that the OHM logo appears as favicon & in header
  - [ ] Verify "historical" language throughout
  - [ ] Verify responsive design of all features work correctly
- Explore Projects
  - [ ] Verify that all drop-down options are filtering and sorting projects correctly
  - [ ] Go to one of the projects and verify that the stats are loading
- Task contributions
  - [ ] Verify that the map feature is working correctly
  - [ ] Verify that task selection for mapping are working correctly: Select a task, map selected task
  - [ ] Task editing in JOSM
  - [ ] Task editing in iD editor
  - [ ] Mark a task as mapped/validated
- My Contributions
  - [ ] Verify that contributions Stats, Projects, Tasks and Teams load correctly
- Manage page
  - [ ] As admin user, check the projects management functionalities
  - [ ] Project creation by drawing an AOI and by uploading a file
  - [ ] Team creation
  - [ ] Organization creation
