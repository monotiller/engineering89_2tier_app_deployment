# 2 tier app deployment
![](images/ec2.png)
## Deploy steps
1. Copy code from host machine to AWS ec2 instance
2. Install required dependencies for node app
3. npm install
4. npm start
5. Should see node app with public ip port 3000

## Second iteration
1. Reverse proxy with nginx so we can get the node app working in the browser without the port

## Third iteration
1. Spin up another ec2 instance with same ubuntu 16.04 to set up MongoDB

## Final iteration
1. Connect the app with MongoDB ec2 to see the /posts working in the browser with public IP

Hint: Use scp command (secure copy)

So, how did we end up copying the file?
First, I moved into the directory with the app folder and then just ran this command:
```console
scp -i "/Users/monotiller/.ssh/eng89_devops.pem" -r  "app" ubuntu@ec2-3-250-106-255.eu-west-1.compute.amazonaws.com:app/
```

## Case scenario (on site)
Clients have an app running on vagrant or any other software and they want to migrate to cloud.

We have done 50% of the things already (AWS account, keys, etc) - We might have to do this ourselves in the future.

All of us have access to AWS instances and other AWS services.

The client's app is working on a monolith architecture, we should migrate it to cloud and make it highly available.

Before moving on to n-tier architectures, during end of sprint, always talk to clients to see that everyone is on the same page.
