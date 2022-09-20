[[Timeline]]

# Command rundown

After running `npm install` in the cloned repository, the following commands are all you need to run the application.

## `npm run startup`
Specified in the `process.json`, the application is set up to start 9 processes.
`pm2` is used to spin these up, and to maintain their up-time.

When run, they will run as background processes.

Each process will spin up a "frontend" and a "backend" (these names should be changed).

The frontend is served locally, on even ports from 59000-59016. This is where the timeline will be displayed.

The backend is also served locally, on odd ports from 59001-59017, although it will most likely not be used, as it will get mirrored through `localtunnel`.

Example: Server 01, served at frontend:59000 and backend:59001.
The timeline can be accessed from `localhost:59000`, and the backend can be accessed from `59001.loca.lt`. The exposed url will hook onto the local frontend and send all its request to it.

[VIDEO]

## `npm run monitor`
To see details and output from the servers, run this command.

It "spawns" an interactive interface in the terminal, that shows resource usage, and up-time status.

## `npm run shutdown`
Basically just shuts the whole thing down. It closes all the active servers.

## `npm run clear`
Should there be left-over logs from earlier runs, or the startup becomes slow, this clears the logs from earlier.