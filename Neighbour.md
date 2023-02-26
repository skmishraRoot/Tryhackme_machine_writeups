A Easy machine from try hack me. Start the machine and lets hack our way to the flag.

Web page at `http://target-IP`

![Pasted image 20230226102435](https://user-images.githubusercontent.com/115337317/221393615-9ffc5fd9-e533-483f-bc39-f79a0280da02.png)

Lets check the page source code for any interseting info.

![Pasted image 20230226102649](https://user-images.githubusercontent.com/115337317/221393626-a43294a4-9d7a-45ec-bfb6-c0cae05276dc.png)


So there is an interseting comment in the source code which tell us two things.
1. We got valid creds to login.
2. There is an admin account on the page.
   
Lets login and enumerate further.

![Pasted image 20230226102945](https://user-images.githubusercontent.com/115337317/221393649-698eb41d-10a6-46e5-95bb-1b149a3f1b02.png)

Page source of the page.

![Pasted image 20230226103000](https://user-images.githubusercontent.com/115337317/221393662-23ae1f85-c690-4e45-b576-17a40cbb8fbf.png)


Again we got some hint by the applicaiton. Admin account is vulnerable to something and we are advised to not peep  neighbor's profile. There can be two possiblites may be we can login to the admin account by using that vulnearbility or there's a way  to see others profile on the website.

If we pay attention to the url we can see our account name in the url. This can be vulnerable to IDOR.  

![Pasted image 20230226103349](https://user-images.githubusercontent.com/115337317/221393678-8e80e549-fe53-4074-9361-aa7c6d426407.png)

what is IDOR?

Insecure direct object references (IDOR) are a type of access control vulnerability that arises when an application uses user-supplied input to access objects directly. The term IDOR was popularized by its appearance in the OWASP 2007 Top Ten. However, it is just one example of many access control implementation mistakes that can lead to access controls being circumvented. IDOR vulnerabilities are most commonly associated with horizontal privilege escalation, but they can also arise in relation to vertical privilege escalation. 
For more info visit [PortSwigger](https://portswigger.net/web-security/access-control/idor) .

When I tried to change user from guest to admin. we logged into as admin and got our flag for the machine.

![Pasted image 20230226104041](https://user-images.githubusercontent.com/115337317/221393697-6b59b123-f806-4046-a0bb-33b9bbea603c.png)


Yay, We completed our machine. 

*Advice* : This machine is very easy but all are not same so be careful while looking for vulnerability anything can be vulnerable. Pay attention to the details because in cybersecurity folks say "devil in the details"
