# DW Conference

This cloud-based API server lets you organize conferences and sessions, and currently has following functionality:
- User authentication
- Create, read, update conferences
- Register/unregister for conferences
- Create and read sessions for conferences
- Add/remove sessions to user's wishlist

This project, the fourth in [Udacity’s Full Stack Web Developer Nanodegree](https://www.udacity.com/course/nd004), focuses on using Google Cloud Platform to develop a scalable web app, and it's built with Google App Engine (Python), Google NDB Datastore, and Google Cloud Endpoints.
<br>

You can check out the demo web page at https://dw-conference.appspot.com
Currently, the demo page does not support all functionality.
You can find out all APIs at [here](https://apis-explorer.appspot.com/apis-explorer/?base=https://dw-conference.appspot.com/_ah/api#p/conference/v1/)


## Project Detail

### Task 1: Add Sessions to a Conference

Most of functionality for the Session class is referenced from existing Conference class, since they both have similar characteristics. 

### Task 2: Add Sessions to User Wishlist

This was also referenced from conference registration functionality, but even simpler.

### Task 3: Work on indexes and queries

Instead of creating some predefined queries, the `querySession` method was implemented to be more flexible. It can have queries with following fields: `START_TIME`, `TYPE_OF_SESSION`, `SPEAKER`, and `DURATION` (but it can't have more than one inequality filter, as same as `queryConference`).

The query problem is implemented by `queryProblem` API method. Since Google Datastore does not allow more than one inequality filter, I just made two separate queries and filter one by another. So the additional inequality logic is implemented by Python.

### Task 4: Add a Task

`getFeaturedSpeaker` method uses memcache to store the featured speaker, and the featured speaker is the one who speaks for more than one session.



## Products
- [App Engine][1]

## Language
- [Python][2]

## APIs
- [Google Cloud Endpoints][3]

## Setup Instructions
1. Update the value of `application` in `app.yaml` to the app ID you
   have registered in the App Engine admin console and would like to use to host
   your instance of this sample.
1. Update the values at the top of `settings.py` to
   reflect the respective client IDs you have registered in the
   [Developer Console][4].
1. Update the value of CLIENT_ID in `static/js/app.js` to the Web client ID
1. (Optional) Mark the configuration files as unchanged as follows:
   `$ git update-index --assume-unchanged app.yaml settings.py static/js/app.js`
1. Run the app with the devserver using `dev_appserver.py DIR`, and ensure it's running by visiting your local server's address (by default [localhost:8080][5].)
1. (Optional) Generate your client library(ies) with [the endpoints tool][6].
1. Deploy your application.


[1]: https://developers.google.com/appengine
[2]: http://python.org
[3]: https://developers.google.com/appengine/docs/python/endpoints/
[4]: https://console.developers.google.com/
[5]: https://localhost:8080/
[6]: https://developers.google.com/appengine/docs/python/endpoints/endpoints_tool
