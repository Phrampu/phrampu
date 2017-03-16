![phrampu](/phrampu.png)

Install:
  1. pip3 install -r requirements
  2. python3 server.py

To-do:
  - Backend:
    - [x] Add logging (replace all print stmts)
    - [ ] Standardize api responses and document
      - [x] Endpoint that just spits out the log file (literally just print it to the screen, would be really nice for debugging)
      - [x] Endpoint that spits out a dict of {threadnum: isalive(bool)}. This could easily be implemented by making an array of timestamps, one for each thread. Whenever a thread sshs and returns, get the timestamp from the wholist and replace the old saved thread timestamp. If the timestamp is ever > 10 mins, then it's dead.
      - [x] Endpoint that spits out a dict of {cluster: 'number of free lab machines'} for frontend use
      - [x] Endpoint that finds the last machine a user was ttyd into
      - [x] Add idle time based on 'w' script
      - [ ] Add additional logging, outside of log table. Could Log stats per lab machine per cluster. So we could query and get usage for the past 24 hours or something. Same thing for users
      - [ ] Endpoint for dumping data based on query
      - [ ] Endpoint + front end for lname search (career acc => name, name => career acc)
    - [x] Figure out how to get lab class schedules + display "HAAS 257 has a class going on right now!" or something
    - [ ] SQLAlchemy ORM + add models for users, etc
    - [x] Move everything to a non-shitty web framework: flask/django.
    - [x] Split out thread slave stuff into another file
    - [x] Split out helper functions into another file (util.py or helper.py)
    - [x] Make hostnames ordered within cluster within master/cluster api calls, i.e., {escher: [{escher00}, {escher01}, ...] instead of random order
  - Frontend:
    - [ ] Filtering by tty/pts
    - [ ] Display traffic graph/heatmap (d3)
    - [ ] Rewrite using an actual framework (angular/react), look into react-native
  - Etc:
    - [ ] Make adjacency lists for every lab room, where each node is a hostname, and the edges are between adjacent lab machines
    - [ ] Swagger docs
