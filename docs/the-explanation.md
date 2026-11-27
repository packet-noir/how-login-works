# Explain the Following

"I click login at work and land in Salesforce without typing a password there.
Walk me through everything that happened."

## My Explanation: 
Salesforce is likely set up to trust another application called an IdP that can verify you are who you claim to be.
When you click login, Salesforce will know which IdP to redirect you to. 
The IdP is also configured to expect authentication requests from Salesforce.
This trust relationship is established via configurations made in both systems.
After the IdP authenticates you, it will deliver signed proof back to Salesforce.
Salesforce then uses this signed assertion to grant you entry and access based on the information about your identity. All while Salesforce
remains completely oblivious about your credentials.
