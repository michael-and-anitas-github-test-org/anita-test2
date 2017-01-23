# Simple-Facebook

### UI:
- Posts on Wall
    - Comments on Posts
- Lists of friends
    - Direct Message Chats
    - Posts on Wall
        - Comments on Posts


### MODELS:

```
{
    wall: {...},
    friends: [...],
    selectedFriend: "Anita"
}
```

```
{
    wall: {
        posts: [


        ]
    },
    friends: [
        {
            name: "Anita"
            messages: [

            ],
            wall: {
                posts: [
                    {
                        message: "I ate a frog, here's what that looked like",
                        picture: "http://blah/frog.gif",
                        sender: "Adrita",
                        sentAt: "2017-01-23T04:58:17.790Z",
                        comments: [
                            {
                                message: "Yummy",
                                sender: "Michael",
                                sentAt: "2017-01-23T04:58:17.790Z"
                            },
                            {...},
                            {...}
                        ]
                    },
                    {...},
                    {...}
                ]
            }   
        },
        {
            name: "Michael"
            messages: [],
            wall: {...}
        },
        ...
    ]
}
```

### CONTROLLERS:

1. Handle Posting Posts
2. Handle Posting Comments
3. Handle Posting Messages
4. Handle selecting Friends
5. Handle server updates to Posts
6. Handle server updates to Comments
7. Handle server updates to Messages
8. Handle Misc stuff (account management, log out, etc...)

### VIEWS:

* Status Text Input for entering whats on your mind OR posting to someone's wall
    - EVENTS: On hitting SEND: Triggers "Handle Posting Posts" controller
* Post List
    * EVENTS: Listens for changes to the POSTS model so it can add new Post Items, DELETE posts, etc...
    * Post Item
        * Message Text
        * Sender
        * Timestamp
        * Comment List
            * EVENTS: Listens for changes to the comments model
            * Comment Item
                * Sender
                * Timestamp
                * Message Text
        * Comment Text Input
        * EVENTS: Notifies controller when user enters comment
* Message List (hidden if no user is selected)
    * Message Item
    * Message Text Input
    * EVENTS: Notifies controller when user enters message
* Friend List
    * Friend Item
        * Friend Name
        * Friend Status
    * EVENTS: Listens for changes to friends model


