# RealMeets events management platform
## By Niccolò Fredducci

### Project choices:
  - Project type: full-Stack Web Application
  - Framework used: Django

### App description:
The purpose of this web application is for people to organize meets of any kinds, see how many people want to attend and decide how they will organize the meet.

### Features
Managers can create any number of events and are then able to read, update and delete those events as well as remove some participants from the attendance list.
Users can read all events, choose to participate in any of them and are then able to see all events which they are attending in a dashboard and choose to unattend.
Admins, managers who are superusers, can do what managers can but for all events and not just their own. They can also access the Django admin page to manually change things.
People who are not logged in are considered guests which can see all events, but upon trying to attend an event, are redirected to the log in page.
Guests can log in or sign up (only as users, manager accounts have to be added manually by an admin) and users are able to sign out.

### Installation instruction
  - Clone the repo: <pre>```git clone https://github.com/NiccoFredducci/RealMeets```</pre>
    - **[WINDOWS only]** If you're on Windows use Windows subsystem for Linux: <pre>```wsl```</pre>
  - Enter the directory: <pre>```cd RealMeets```</pre>
  - Create a virtual environment: <pre>```python -m venv venv```</pre>
  - Enter the virtual environment: <pre>```source venv/bin/activate```</pre>
  - Build: <pre>```pip install -r requirements.txt && python manage.py migrate && python create_users.py```</pre>
  - Run: <pre>```python manage.py runserver```</pre>
You will see a local address in the terminal from which you will be able to access the page.

### Database
`db.sqlite3` is the name of the database used by the app when you run it locally. It will contain 8 sample events: 4 created by a manager and 4 created by an admin.

### Demo accounts
Username / Password:<br>
admin_demo / admin12345 (a sample account for a superuser)<br>
user_demo / user12345 (a sample account for a subscriber)<br>
manager_demo / manager12345 (a sample account for a manager)

### Online deployment
An online instance of this web app is running on Render and can be accessed through the link: https://realmeets.onrender.com/.<br>
**NOTE:** Given the ephemeral nature of the online service, the events and/or users might not be populated in the database after the web app has been online for a while.

## Testing Scenario
### To evaluate each feature you could:
Sign up as a new user, attend several events, log out, sign in with the "user_demo" account, withdraw from an event and log out.<br>
Sign in to the "manager_demo" account, open an event, remove some participants, if there are any, (you can then check from the users' account later whether the participation in the event has been removed), edit the event with whatever change you would like, save the changes, open another event and delete it through the edit page, try to create a new event.<br>
Sign in to the "admin_demo" account, do the same things you did with the manager account except for the fact that you can do so with all the events (not just created by the admin account but also the ones created by the manager account), you can also use the "/admin" page to manually create manager accounts. (you have to append "/admin" to the home URL as I thought it was best not to include a button)
