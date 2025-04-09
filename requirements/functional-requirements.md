# Functional Requirements

## 1. User Authentication
- Users authenticate via Google OAuth2 with JWT token management  
- Role-based access control (User, Admin)  
- Profile management capabilities  

**Endpoints**:  
`POST /auth/login` - Initiate OAuth2 login flow  
`GET /auth/me` - Retrieve authenticated user details (including role)  
`PUT /auth/update-profile` - Update user profile information  

## 2. User Service
- Manages user-community relationships and preferences  
- Stores content filters and notification settings  
- Enables role-based access control  

**Features**:  
- Tracks all communities a user follows/interacts with  
- Provides user data to other services (Feed, Search, Notification)  

## 3. Community System
- Users can browse and join existing communities  
- Admins have full community management capabilities  

**Endpoints**:  
`GET /communities` - List all available communities (with pagination)  
`POST /communities` - Create new community (Admin only)  
`PUT /communities/:id` - Update community details (Admin only)  
`DELETE /communities/:id` - Delete community (Admin only)  
`POST /communities/:id/join` - Join existing community  
`DELETE /communities/:id/remove-user/:userId` - Admin removes user from community  

## 4. Post System
- Members can create, edit and interact with posts  
- Like functionality with real-time updates  

**Endpoints**:  
`POST /posts` - Create new post in community  
`PUT /posts/:id` - Edit existing post  
`DELETE /posts/:id` - Delete post  
`POST /posts/:id/like` - Like/unlike a post  
`GET /posts/community/:id` - View paginated community posts (max 50 per request)  

## 5. Stories System
- Temporary content with 24-hour expiration  
- Auto-deletion after expiration period  

**Endpoints**:  
`POST /stories` - Create ephemeral story  
`GET /stories/community/:id` - View active community stories  
`DELETE /stories/:id` - Delete story (user or admin)  

## 6. Feed Service
- Personalized content feed with recommendation system  
- Suggests posts based on popularity and engagement  

**Endpoints**:  
`GET /feed` - Retrieve personalized feed for authenticated user  
`GET /feed/recommended` - Get recommended posts  

## 7. Search Service
- Platform-wide content search functionality  
- Indexes data from multiple sources  

**Features**:  
- Scalable search infrastructure  
- Future support for hashtags and trending topics  

## 8. Admin Features
- Comprehensive moderation capabilities  
- User and content management  

**Endpoints**:  
`DELETE /admin/users/:id` - Remove user from platform  
`DELETE /admin/posts/:id` - Remove inappropriate posts  
`DELETE /admin/stories/:id` - Remove stories  

## 9. Notification System
- Real-time event-based notifications  
- Multiple notification types  

**Endpoints**:  
`GET /notifications` - Retrieve user notifications  
`POST /notifications/send` - Push notification to user  