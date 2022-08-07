[[Timeline]]

# Timeline

- [ ] Frontend
	- [ ] Convert styling from timeline-project
	- [ ] Setup QR code
- [ ] Backend
	- [x] Setup functionality to control the frontend
	- [ ] Style the functionality


# Setup and run

Clone repo and run `npm install`.

Make sure you have "PM2" installed globally (assuming nodeJS is already installed). If it's not installed, run `node i pm2 -g`.

The start the program run `npm run startup`, and it will spin up 6 instances of the server, and prompt you into the `pm2 monit` monitor where logs are shown for each instance.

If not output through the terminal, the ports for each server is:

| Server   | Frontend | Backend |
|:-------- |:-------- |:------- |
| Server 1 | 59000    | 59001   |
| Server 2 | 59002    | 59003   |
| Server 3 | 59004    | 59005   |
| Server 4 | 59006    | 59007   |
| Server 5 | 59008    | 59009   |
| Server 6 | 59010    | 59011   | 

---

To shut it down, run `npm run shutdown`. This will stop all the servers, and preserve the logs. To flush the logs, run `npm run clear`.