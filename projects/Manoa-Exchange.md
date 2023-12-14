---
layout: project
type: project
image: img/download (1).png
title: "Manoe Exchange Final Project Website"
# All dates must be YYYY-MM-DD format!
date: 2023-12-13
published: false
labels:
  - HTML/CSS
  - Web Development
  - Meteor
summary: "A website I designed with four other teammates as a final project for ICS 314 that solves the problem of students seeking insight into foreign exchange experiences of fellow students"
---
<img width="440px" height="320px" src="../img/Untitled.png" class="img-thumbnail" >

## Introduction
  Throughout the software engineering 1 course, i gained new skills in html/css and meteor that allowed me to gain more understanding of web development, which in turn allowed me to assist my team in creating the website we elected to make for our final project. Our website "manoa exchange" is a website that seeked to solve the problem that UH Manoa students faced, which is the lack of information to foreign exchange experiences of peers and how to access them.

## Backend
  The portion of the project I had been responsible for was mainly working on the my profile page, and the backend to the website along with another teammate. Our team distributed tasks among the five of us which adhered to our preferences, or availiblity of the task. Our website had a key focus of allowing users/students to create profiles that contain basic information such as school email id and name, and allow them to post information of their hopes or experiences in foreign exchange programs in a way similar to social media apps like twitter and websites like reddit.

  The mypfrofile page was made with a simplistic design where the left portion of the page contained a column composed of 2 react bootstrap card components that contained the user's profile picture, full name, student id number, and email, while the right portion rendered all of the posts the student made in the website. When bulding theb webpage, I managed to learn how to utilize react bootstrap classes better and more efficiently, with the card and grid classes being the most prevalent react 

This is the code for the profile page of the website:

```jsx
import React from 'react';
import { Meteor } from 'meteor/meteor';
import { Link } from 'react-router-dom';
import { Button, Card, Col, Container, Row } from 'react-bootstrap';
import { useTracker } from 'meteor/react-meteor-data';
import LoadingSpinner from '../components/LoadingSpinner';
import { Profiles } from '../../api/profile/Profile';
import { Posts } from '../../api/post/Post';
import { Comments } from '../../api/comment/Comment';
import PostItem from '../components/PostItem';
import '../css/PostItem.css';
import { PageIDs } from '../utilities/ids';
import NavBar from '../components/NavBar';

const MyProfile = () => {
  const { ready, posts, comments, profiles } = useTracker(() => {
    const subscription = Meteor.subscribe(Profiles.userPublicationName);
    const subscription2 = Meteor.subscribe(Posts.userPublicationName);
    const subscription3 = Meteor.subscribe(Comments.userPublicationName);

    const rdy = subscription.ready() && subscription2.ready() && subscription3.ready();

    const profileData = Profiles.collection.find({}).fetch();
    const postData = Posts.collection.find({}, { sort: { createdAt: -1 } }).fetch();
    const commentData = Comments.collection.find({}).fetch();

    return {
      profiles: profileData,
      posts: postData,
      comments: commentData,
      ready: rdy,
    };
  }, []);

  const userProfile = profiles.find(profile => profile.owner === Meteor.user().username);

  return ready ? (
    <div id={PageIDs.myProfilePage}>
      <NavBar />
      <Container className="mb-4">
        <Row className="mt-4">
          <Col lg={4}>
            <Card className="mb-4 rounded border border-dark card_profile antw">
              <Card.Body className="text-center">
                <div className="d-flex justify-content-center mb-4">
                  <img
                    src={userProfile?.profilePicture || 'default-avatar-url'}
                    alt="avatar"
                    className="rounded-circle border border-dark"
                    style={{ width: '150px', height: '150px' }}
                  />
                </div>
                <Link to="/uploadWidget"><Button className="custom-update-button">Add/Edit Profile Picture</Button></Link>
                <h3 className="mb-1 mt-3">{userProfile?.firstName || 'Insert Name'} {userProfile?.lastName || 'Insert Name'}</h3>
                <p className="text-muted mb-4">{userProfile?.idNumber}</p>
              </Card.Body>
            </Card>
            <Card className="mb-4 mt-4 border border-dark antw">
              <Card.Body>
                <Row className="mb-2">
                  <Col sm="3">
                    <Card.Text>Name</Card.Text>
                  </Col>
                  <Col sm="9">
                    <Card.Text className="text-muted">{userProfile?.firstName || 'Insert Name'} {userProfile?.lastName || 'Insert Name'}</Card.Text>
                  </Col>
                </Row>
                <Row>
                  <Col sm="3">
                    <Card.Text>E-mail</Card.Text>
                  </Col>
                  <Col sm="9">
                    <Card.Text className="text-muted">{userProfile?.owner || 'Insert Name'} </Card.Text>
                  </Col>
                </Row>
              </Card.Body>
            </Card>
          </Col>
          <Col lg={8}>
            <Card className="mb-4 border border-black antw">
              <Card.Header as="h3" className="text-center">Recent Posts</Card.Header>
            </Card>
            {posts.map((post) => {
              const relatedComments = comments.filter(comment => comment.uniqueId === post._id);
              return (
                <Col md={12} key={post._id} className="mb-4">
                  <PostItem
                    post={post}
                    comments={relatedComments || []}
                  />
                </Col>
              );
            })}
          </Col>
        </Row>
      </Container>
    </div>
  ) : <LoadingSpinner />;
};

export default MyProfile;
```
<img width="540px" height="440px" src="../img/Favorite Animations - Google Chrome 9_1_2023 11_01_46 PM (2).png" class="img-thumbnail" >
