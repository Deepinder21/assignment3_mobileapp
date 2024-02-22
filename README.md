# Assignment: Architectural Decisions

Ethan Schwab

Deepinder Singh Aulakh

## Architecture decision 1: Choice of Native App Development

### Context
Team needs to decide app development approach for transportation app. Team needs to consider factors such as performance, features and user experience. Team should select an approach that provides optimal performances and platform-specific features. It should also ensure seamless and responsive experience across various mobile devices and platform.

### Decision 
We will create a native app for both android and iOS.

### Rationale

#### Response to Forces:
Native app allows us to utilize platform features in much more efficient way and provide superior performance compared to web and hybrid apps. This also ensures a smoother and much responsive app which is essential for a transportation app.
Native apps offer better integration with device hardware and operating systems, resulting in more engaging app which aligns with goals of transportation company of providing a modern and user-friendly app.

### Rejected Alternatives:
**Web App:** While web apps offer cross-platform compatibility and easier maintenance, they often lack the performance and native functionality required for a transportation app with real-time tracking and updates.

**Hybrid App:** Hybrid apps provide a compromise between native and web apps, but they may suffer from performance issues and limitations in accessing platform-specific features compared to native development.

### Status
Accepted

### Consequences
**Optimal Performance:** Native app development ensures superior performance providing a better user experience.
**Platform-specific features:** native app development allows us to use platform-specific features which results in enhancing app’s functionality.
**Increased Development Time:** Developing separate native app for iOS and android might be time consuming.
**User Satisfaction:** By delivering a native app with a smooth and intuitive user experience, which will result in user satisfaction.

## Architecture decision 2: Selection of UI framework

### Context
Team needs to choose UI framework for developing the user interface for the mobile application for transportation company. We need to consider factors such as development efficiency, cross-platform compatibility and flexibility in design. The selected UI framework should be able to provide tools for building responsive user interfaces and it should support app development for both android and iOS.

### Decision
Team will be using react native as the UI framework as it is compatible for both android and iOS.

### Rationale
React native is a popular UI framework that allows for efficient development of cross-platform mobile applications. It also offers rich set of components and tools that are essential for building responsive user interface.

React native enables us to write code that can deployed across multiple platforms, including android and iOS. The reduces development time and efforts required to maintain the mobile application.

### Rejected Alternatives
**Native development:** while native development provides optimal performance and specific features but requires different codes for android and iOS which increases development time and complexity.

**Hybrid frameworks:** Hybrid frameworks offer cross-platform compatibility but has issues in accessing native features compared to React Native.

### Status 
Accepted

### Consequences

**Efficient development and Cross-platform compatibility:** As react native is compatible with both android and iOS it allows rapid development reducing development time and efforts. It also ensures consistency across various platforms and reduced maintenance time.

**Rich UI Components:** React native provides a rich set of UI tools required for building a responsive and visually appealing user interface, enhancing overall experience.

**Community Support:** React Native has many users, providing access to a large number of resources, tutorials helping in ongoing development and maintenance efforts. 


## Architecture decision 3: Selection of Backend Language

### Context 
Team must decide on the backend language for developing the server components and logic for modern transportation mobile app. Factors such as performance, developer expertise and ecosystem should be considered. The selected language should offer features for building scalable and efficient server-side application. Team should also consider their expertise and familiarity with the chosen language.

### Decision
We will go with JavaScript using Node.js and Express.js as the backend language and framework for developing the components of mobile app.

### Rationale
Node.js is a popular and widely adopted JavaScript runtime that offers event-driven architecture to users that makes it widely suited for building real time applications.
The team has extensive expertise in JavaScript making node.js and express.js a natural choice for backend development. This will ensure efficient development and allows for rapid iteration and prototyping.

### Rejected alternatives:
**Java:** While java offers strong performance and scalability, it may require deeper learning curve compared to node.js.

**Python:** python is known for its compatibility, simplicity but it may not offer the same level of performance as node.js for real time application.

### Status 
Accepted 

###Consequences 
**Performance and Scalability:** Both Node.js and Express.js provides a scalable and efficient backend solution, capable of handling real-time updates in mobile app.

**Developer Efficiency:** As JavaScript can be used for both frontend and backend development, it allows better collaboration between both teams. 

**Ecosystem Support:** Node.js has a large and active ecosystem with a wealth of libraries and modules, facilitating rapid development and integration of third-party services.



## Architecture decision 4: Access to Permissions

### Context 
Team must decide on what parts of the mobile device the app has permission to access. The only major factor that is needed to be considered is function. The selected permissions should enable the app to function as intended and should not have any more. Team should also consider their expertise and familiarity with the chosen permissions.

### Decision
We have decided that the app should have access to your location and images. 

### Rationale
The transportation app needs to be able to see your location to provide accurate restaurant recommendations, estimate delivery times, and display nearby options. So it needs this permission.

Access to your saved images is there so you can change your profile picture. Because we will be including a profile picture for your account.

### Status 
Accepted 

### Consequences 
**Customization:** The app can be customized to an extent with the ability to change your profile photo. 

**Location Automation:** The user does not have to manually input their location to find delivery times, restaurant recommendations, or display nearby options. The app will do that for the user automatically.



## Architecture decision 5: Data Storage

### Context 
To store user profiles, ride history, and payment information, the team needs to select appropriate data storage methods. Team must decide on how the app will store data. Considerations taken into account when selecting how the app stores data should include data integrity and scalability, along with the team’s familiarity with the data storage technique.

### Decision
We have decided to use cloud storage to store the app’s data. Specifically, Google Cloud databases.

### Rationale
This is because it’ll allow for us to save a lot of costs while still granting access to the other two types of data storage. We do not have to build our own database of things when we can use someone else's data storage.

We chose Google because it is reputable and safe.

### Rejected alternatives:
**NoSQL Database Management System:** NoSQL databases are a type of database that stores data in a non-tabular form, such as key-value pairs, document-based data, and graph data. This storage solution is used for storing unstructured data such as social media posts, images, and videos. This was rejected because we aren’t storing those.

**Relational Database Management System (RDBMS):** This type of storage solution is commonly used for storing structured data such as user, product, and inventory data. We will probably be using this structure, but not the system itself. The system will be managed by google cloud databases.

### Status 
Accepted 

### Consequences 
**Low initial cost:** We don’t have to pay anywhere close to as much money to store data as we would if we had decided to build our own data storage.

**Higher maintenance cost:** We must pay google to use their services. This is manageable if we are making more money than we pay to google.


## Architecture decision 6: Real-Time Communications

### Context 
To track the driver and passenger locations in real-time, the app requires continuous updates. The team should figure out what technologies to use to enable seamless real-time location updates. The app needs a push technology.

### Decision
We have decided to use Server Side Events to enable real-time communication and location tracking.

### Rationale
It’s not necessary to send data from client to server here. We’re just having the trains and busses update their location info on people’s phones. This does not really need client to server communication, just server to client.

### Rejected alternatives:
**WebSockets:** WebSockets are bidirectional, which is not what we need. We are not having the phone update its location on the bus or train server. WebSocket would be overkill. It’s always wise to use the best tool for the job.

### Status 
Accepted 

### Consequences 
**Inability for phones to communicate with vehicles:** We don’t have to pay anywhere close to as much money to store data as we would if we had decided to build our own data storage.
**Better performance:** WebSocket is *generally* more performance intensive than SSEs. So using SSEs enables slightly better performance.


## Architecture decision 7: Mapping Service

### Context 
The team should choose a mapping service and routing algorithm that meets the transportation company's requirements, considering factors such as accuracy, traffic data, and customization options.

### Decision
We have decided to use Valhalla as our routing engine and algorithm.

### Rationale
Valhalla is both open source and also one of the few routing engines that works with everything from trucks to transit to cars. 

### Rejected alternatives:
**OSRM:** Was rejected because it didn’t work with trucks or transit.

### Status 
Accepted 

### Consequences 
**Setup:** It’ll take a bit to learn how to use Valhalla given that its documentation is a little thin.
**Features:** Valhalla has all the standard features of routing, isochrones and matrix, but also additionally offers map matching, multimodal routing, elevation querying, a simple Traveling Salesman solver and a fully integrated Python SDK. The app will use this to its advantage.


## Architecture decision 8: Selection of Push Notification Service Provider

### Context
The team needs to choose a push notification service provider to implement a system for push notifications for the mobile app. Team needs to consider app features and a system that supports both android and iOS. System should also provide option to personalize messages to deliver relevant notifications to the users.

### Decision 
Team will be using Firebase Cloud Messaging (FCM) as the push notification provider for the app.

### Rationale
FCM supports both android and iOS which enables us to provide a unified solution for both platforms. Unlike, Apple Push Notification Service (APNs) which only allows iOS devices for push notifications. 
FCM offers a lot of features for personalizing and message targeting, allowing users to engage with notifications according to their preferences and behavior. 

### Status
Accepted

### Consequences
**Cross-platform Support:** Firebase Cloud Messaging (FCM) provides support to both android and iOS platforms, ensuring that each uses receives notifications.
**Reliability and Scalability:** FCM offers both Reliability and Scalability, which makes it capable of handling large numbers of notifications.
Ease of Integration: Integration of FCM into mobile app is very easy and straightforward, with support provided by Firebase, which reduces development time and efforts required. 

