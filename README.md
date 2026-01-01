<h1>Sijal – AI-Powered Interview Preparation Platform</h1>

<p>
Sijal is an intelligent interview preparation platform designed to help job seekers
experience realistic interview simulations and receive actionable feedback.
The platform combines AI-powered analysis with human HR evaluation to provide
a comprehensive and practical interview readiness experience.
</p>

<p>
Users can start interview sessions based on their CV or a job description,
participate in voice-based interviews, and receive detailed performance evaluations,
including strengths, weaknesses, and personalized improvement plans.
</p>

<hr/>

<h2>Key Features</h2>
<ul>
  <li>AI-generated interview sessions based on CV or job description</li>
  <li>Voice-based interview simulation using AI agents</li>
  <li>Automated interview analysis with scoring and detailed feedback</li>
  <li>HR-led interview evaluation and professional assessment</li>
  <li>AI-generated personalized improvement and development plans</li>
  <li>Secure authentication and authorization using JWT</li>
  <li>Email notifications for interview session details</li>
</ul>

<hr/>

<h2>System Workflow</h2>
<ol>
  <li>User creates an interview session using CV or job description</li>
  <li>Interview questions are generated dynamically</li>
  <li>User joins a voice interview by calling the provided number</li>
  <li>Interview is recorded and transcribed automatically</li>
  <li>AI analyzes the interview and generates structured feedback</li>
  <li>HR evaluation and scoring are added when applicable</li>
  <li>User receives a detailed analysis and improvement plan</li>
</ol>

<hr/>

<h2>Tech Stack</h2>
<table border="1" cellpadding="8">
  <tr><th>Area</th><th>Technology</th></tr>
  <tr><td>Backend</td><td>Spring Boot, Spring MVC, Spring Data JPA</td></tr>
  <tr><td>Security</td><td>Spring Security, JWT, BCrypt</td></tr>
  <tr><td>Database</td><td>MySQL (AWS RDS)</td></tr>
  <tr><td>AI Integration</td><td>OpenAI API</td></tr>
  <tr><td>Voice Interviews</td><td>Vapi AI</td></tr>
  <tr><td>Email Service</td><td>Spring Boot Mail (SMTP)</td></tr>
  <tr><td>Deployment</td><td>AWS Elastic Beanstalk, EC2</td></tr>
</table>

<hr/>

<h2>API Endpoints Overview</h2>
<table border="1" cellpadding="8">
  <tr>
    <th>#</th><th>Method</th><th>Endpoint</th><th>Description</th>
  </tr>

  <tr><td>1</td><td>GET</td><td>/health</td><td>Application health check</td></tr>

  <tr><td>2</td><td>POST</td><td>/api/v1/interview-session/start-session-with-cv</td><td>Start interview using CV</td></tr>
  <tr><td>3</td><td>POST</td><td>/api/v1/interview-session/start-session-with-description</td><td>Start interview using job description</td></tr>
  <tr><td>4</td><td>GET</td><td>/api/v1/interview-session/get-my-sessions</td><td>Retrieve user interview sessions</td></tr>
  <tr><td>5</td><td>GET</td><td>/api/v1/interview-session/get-session-by-id/{id}</td><td>Retrieve session details</td></tr>
  <tr><td>6</td><td>GET</td><td>/api/v1/interview-session/get_question/{sessionId}</td><td>Retrieve session questions</td></tr>

  <tr><td>7</td><td>GET</td><td>/api/v1/analysis-by-ai/all-analysis</td><td>Retrieve all AI analyses</td></tr>
  <tr><td>8</td><td>GET</td><td>/api/v1/analysis-by-ai/analysis-for-session/{sessionId}</td><td>Retrieve analysis for a specific session</td></tr>

  <tr><td>9</td><td>GET</td><td>/api/v1/questions/questions-for-session/{sessionId}</td><td>Retrieve interview questions</td></tr>

  <tr><td>10</td><td>POST</td><td>/api/v1/vapi/webhook</td><td>Handle voice interview webhook</td></tr>
</table>

<hr/>

<h2>Deployment</h2>
<p>
The backend application is deployed on AWS using a scalable and production-ready setup.
AWS Elastic Beanstalk is used for application hosting, with EC2 handling compute resources
and RDS (MySQL) managing persistent data storage.
</p>

<p>
The system includes health checks and monitoring to ensure application availability
and stability in production.
</p>

<hr/>

<h2>Project Resources</h2>
<ul>
  <li>ERD Diagram: <a href="#">https://lucid.app/lucidchart/0ac588ea-6c47-40ff-9f8c-2ddcc49f0a08/edit?invitationId=inv_dd8ca42c-dd44-4e7e-9f78-089609d925f1</a></li>
  <li>Postman Documentation: <a href="#">https://documenter.getpostman.com/view/51095397/2sBXVbJZNn</a></li>
  <li>Figma Design: <a href="#">https://www.figma.com/design/NIJsffp2YQOJp0cQm8bale/final-project?node-id=0-1&t=wBFLfeHHZzeEQ0Hg-1</a></li>
  <li>Production Domain: <a href="https://sijal.tech">https://sijal.tech</a></li>
</ul>
