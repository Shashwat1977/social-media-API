
# Social Distance

Rest API implemented in Spring Boot and deployed on aws ec2.

## Requirement
Implemented a web-app using java spring-boot. 
Here are the following functionalities :
-  User is able to create his/her profile. 
-  User can add another user in his friend list. Friend list is mutual i.e if A is friend of B, then B is also friend of A.
- A user is also able to remove another user from his friend list. He/Her can also view his friend list.
- Given an input integer K, a user can  view all connections at distance K from him.
- Distance is defined as the minimum steps needed to reach from user A to user B. Some examples for more clarity.
	- For example, if A is a friend of B, then distance of B from A is 1. 
	-  A is friend of B. B is a friend of C. C is a friend of D. Then Distance(A,D) = 3 
	-  A ⇔ B , B ⇔ C, C ⇔ D, D ⇔ E, C ⇔ E. In this case Distance(A,E) = 3 as E can be reached via C.

## Technology stack
- Spring Boot
- Spring Data JPA
- Amazon RDS (MySQL)
- Amazon AWS EC2

## REST API

URL http://ec2-3-132-212-32.us-east-2.compute.amazonaws.com:8080/

|  | Method |	Mapping|
|--|--|--|
| Add new user  | POST  |  /addUser |
| Connect two user as friend   | GET | /addFriend/{uid}/{fid} |
| Remove friendship | DELETE | /removeFriend/{uid}/{fid} |
| Get all connections at K distance from user uid  | GET | /getDistantConn/{uid}/{k} |
| Get friendlist of user with id "uid" | GET | /getFriendList/{uid} |

- Add new user **Post /addUser** 
{
"name" : "user name"
"username" : " unique username"
"email" : " user's email"
}
