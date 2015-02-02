# adegnanCfTest-
Cloud Foundry Testing

## Getting started 

Assuming you've already received the email with your credentials in it, you'll want to install the cloudfoundry-cli package; This can be found here https://github.com/cloudfoundry/cli, there are pre-compiled binaries if you scroll down slightly.  Following that, as suggested, login and change your password using the following two commands:-

- cf login
- cf passwd

## starting an app

- will fill this out later

## Notes on Crippledness

I don't have permission to do the following commands
- cf create-service-broker -  This, I believe, is how we add more services, We'd need this if we want to actually give people the ability to make their own services


## Questions

CF is a PaaS system; it is unclear that we'd get any access to the infrastructure beyond what the APIs give us access to.  

### Security

We need to know whether our infrastructure is using shared resources and how this affects our security.  Follow up questions may be needed depending on these answers.

- What platform is CF running on?  
- Is the CF software shared between clients?
- Are the physical nodes shared?
- Are the underlying virtual machines shared?
- Is the compute platform shared?
- Are any of the storage platforms shared?
- Are any network components shared?
- Where is our entry point to said network?
- Do we have any kind of separation on the network layer?
- Where do our external SSL connections terminate?
- Are there any shared resources beyond this point?

We need to ask any questions about the underlying platform.  This is probably something VMware related and thus it could be useful to ask the similar questions we'd ask regarding the IaaS platform provided by skyscape:

- What are you running on the underlying platform
- Is there a dedicated security team working on the platform?
- What hardware is the platform running on.  Switches, routers, servers, etc?
- How is the underlying platform components patched?
- How and what is monitored on the platform?

We need to ask any CF specific questions, particularly on how this pertains to any shared resources which have been disclosed above.

- How are processed isolated?  Is it possible to isolate at VM level?  CGroup?  User?  Does it run Linux? 
- How does CF persist data?
- How are process created, destroyed, etc?

### Scalability

It's important to know how CF is scaled in general and in this specific install.  

### Features

We need to have an outline on what the platform offers and where the manual tasks lie.  Specifically I want to figure out which tasks will require us to log a ticket and wait.

- Docs suggests that you have to terminate SSL outwith the platform.  Is this still the case?  If so, how do we setup our own SSLs?
- How does it handle new versions of an app deploy.  Does it achieve zero-downtime?
- How do we manage performance?  Does it have a profiler?  
