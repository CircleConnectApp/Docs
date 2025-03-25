# Functional Requirements

## User Authentication
- Users must authenticate via Google OAuth2 to access the system  
**Endpoints**:  
`POST /auth/login` - Initiate OAuth2 login flow  
`GET /auth/me` - Retrieve authenticated user profile  
`PUT /auth/update-profile` - Update user information  

## Community System
- Users can discover and join interest-based communities while admins manage them  
**Endpoints**:  
`GET /communities` - List all available communities  
`POST /communities` - Create new community (Admin only)  
`POST /communities/:id/join` - Join existing community  

## Post System
- Members can create and interact with posts in their communities  
**Endpoints**:  
`POST /posts` - Create new post in community  
`POST /posts/:id/like` - Like/unlike a post  
`GET /posts/community/:id` - View community posts  

## Stories System
- Users share temporary content that disappears after 24 hours  
**Endpoints**:  
`POST /stories` - Create ephemeral story  
`GET /stories/community/:id` - View community stories  

## Admin Features
- Administrators moderate content and manage users  
**Endpoints**:  
`DELETE /admin/users/:id` - Remove user from platform  
`DELETE /admin/posts/:id` - Remove inappropriate posts  

## Notification System
- Users receive real-time updates for relevant activities  
**Endpoints**:  
`GET /notifications` - Retrieve user notifications  
`POST /notifications/send` - Push notification to user  