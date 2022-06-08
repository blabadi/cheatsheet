# Configuring oidc login with only 1 oauth provider (google) + OTP  
- configure identity provider in the realm -> google
![image](https://user-images.githubusercontent.com/8655252/172668014-e5ef377f-3890-4346-a330-71fcb5368b8e.png)

- copy browser flow
- keep only identity redirector

- configure identity redirector to default to "google"
 ![image](https://user-images.githubusercontent.com/8655252/172668165-9f6dd7c6-5a77-4ffc-91db-56342a98584c.png)

- add new flow to run as post login to force OTP
![image](https://user-images.githubusercontent.com/8655252/172668301-22ede82d-5862-459a-8e5f-43eb5914aba0.png)

- edit the identity provider to run that as post login flow
![image](https://user-images.githubusercontent.com/8655252/172668410-8eae1f30-d884-46a4-a5ac-b167f2e97f7d.png)

- create the client that will use keycloak as oidc provider and configure the browser flow to use the identity provider redirector
![image](https://user-images.githubusercontent.com/8655252/172668682-e2dcfef0-cd74-41f9-9657-098be160a0e2.png)


- if more than provider needed, the authentication flow needs to show a login form to select the provider 
