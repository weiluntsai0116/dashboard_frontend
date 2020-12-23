## dashboard.github.io

### App location:
- User node: http://dashboard-env-1.eba-szsfmavw.us-east-2.elasticbeanstalk.com/
- Demo mode: http://dashboard-env-1.eba-szsfmavw.us-east-2.elasticbeanstalk.com/?token=demo

### Content to be refine: deadline: 12/E
1. Tech stacks:
    - Dash (Plotly)
    - AWS CodePipeline
    - AWS Elastic Beanstalk
    - AWS RDS (MySQL)
    - JWT/ Fernent
2. Instructions:
    - User's operation:
        1. write a python dash code containing their dash figure.
        2. test their python dash code using the test procedure we provided.
        3. generate an HTML file by running their python program that inserted with the pio.write command we provided.
    - Dashboard's operations:
        1. Create:
            - download template dashcode
            - A signal_id will be given
            - upload and display the template dashcode
        2. Read:
            - display dashcode
        3. Modify:
            - upload and display dashcode
            - update signal info in db
        4. Delete:
            - delete dashcode and signal in db
    - Dashboard receives a GitHub link containing the HTML file.
    - The uploading procedure renames the HTML file, uploads it to our GitHub, and returns the new link to Dashboard
---
Notes:
1. Issues when deploying the dashboard on Elastic Beanstalk:
    - Port number must align with the one Elastic Beanstalk is using.
      you can check EB log for the information.
    - File name must be ***application.py***
    - Must use ***application=app.server*** and ***application.run***
    - Keep the requirements.txt is concise as possible
2. Development steps:
    - Write some dashcode for figures
    - Gen html for embed
    - Host the html files on GitHub Page and get the URLs.
    - Embed the URLs in application.py 
    - upload application.zip to Elastic Beanstalk
        - any changes on GitHub will trigger the upload process (AWS CodePipeline)
