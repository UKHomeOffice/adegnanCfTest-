# adegnanCfTest-
Cloud Foundry Testing

## Getting started 

Assuming you've already received the email with your credentials in it, you'll want to install the cloudfoundry-cli package; This can be found here https://github.com/cloudfoundry/cli, there are precompiled binaries if you scroll down slightly.  Following that, as suggested, login and change your password using the following two commands:-

- cf login
- cf passwd

## starting an app

- will fill this out later

## Notes on Crippledness

I don't have permission to do the following commands
- cf create-service-broker -  This, I believe, is how we add more services, We'd need this if we want to actually give people the ability to make their own services


## Questions

Cloudfoundry is a PaaS system; it is unclear that we'd get any access to the infrastructure beyond what the APIs give us access to.  

### Security

We need to know whether our infrastructure is using shared resources and how this affects our security.

- What platform is cloudfoundry running on?  
- Is the cloudfoundry software shared between clients?
- Is the compute platform shared?
- Are the underlying virtual machines shared?  
- Are the physical nodes shared?
- How does CF persist data?
- Are any of the storage platforms shared?
- Are any network components shared?
- Where is our entry point to said network?
- Do we have any kind of separation on the network layer?
- Where do our external SSL connections terminate?
- Are there any shared resources beyond this point?

We need to ask any questions about the underlying platform.  This is probably something VMware related and is probably similar to the IaaS platform provided by skyscape:

- Fill this our later

- We need to ask any cloudfoundry specific questions, particularly on how this pertains to any shared resources which have been disclosed above.


### Scalability

### Features

We need to have an outline on what the platform offers and where the manual tasks lie.  Specifically I want to figure out which tasks will require us to log a ticket and wait.

- Research suggests that you have to terminate SSL outwith the platform.  Is this still the case?  If so, how do we setup our own SSLs, where do these terminate, and who else shares the onfrastrcuture 
