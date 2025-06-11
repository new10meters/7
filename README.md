App.js

import React from "react"; 
import ProfileCard from "./ProfileCard"; 
import "./App.css"; 
function App() { 
return ( 
<div className="app"> 
<ProfileCard 
name="Joy" 
bio="A passionate software developer with a love for creating impactful solutions." 
profilePicture="https://randomuser.me/api/portraits/women/80.jpg" 
backgroundColor="#fff666" 
/> 
</div> 
); 
} 
export default App; 

  
App.css 

.app { 
display: flex; 
justify-content: center; 
align-items: center; 
height: 100vh; 
background-color: #f0f0f0; 
} 



ProfileCard.js 

import React, { useState } from "react"; 
import "./ProfileCard.css"; 
function ProfileCard({ name, bio, profilePicture, backgroundColor }) { 
const [hovered, setHovered] = useState(false); 
const cardStyles = { 
backgroundColor: hovered ? '#e0e0e0' :backgroundColor, 
transform: hovered ? "scale(1.05)" : "scale(1)", 
transition: "transform 0.3s ease, box-shadow 0.3s ease", 
boxShadow: hovered 
? "0px 4px 20px rgba(0, 0, 0, 0.2)" 
: "0px 2px 10px rgba(0, 0, 0, 0.1)", 
}; 
return ( 
<div 
className="profile-card" 
style={cardStyles} 
onMouseEnter={() => setHovered(true)} 
onMouseLeave={() => setHovered(false)} 
> 
<img 
src={profilePicture} 
alt={`${name}'s profile`} 
className="profile-picture" 
/> 
<h2 className="profile-name">{name}</h2> 
<p className="profile-bio">{bio}</p> 
</div> 
); 
}; 
export default ProfileCard;


ProfileCard.css 

.profile-card { 
width: 300px; 
padding: 20px; 
border-radius: 15px; 
text-align: center; 
margin: 20px auto; 
} 
.profile-picture { 
width: 100px; 
height: 100px; 
border-radius: 50%; 
object-fit: cover; 
margin-bottom: 15px; 
} 
.profile-name { 
font-size: 1.5rem; 
font-weight: bold; 
color: #333; 
margin-bottom: 10px; 
} 
.profile-bio { 
font-size: 1rem; 
color: #555; 
} 
