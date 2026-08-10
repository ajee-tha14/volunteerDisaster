# Problem Statement

## 1. Title

Volunteer Disaster Relief Coordination System

## 2. Domain

Disaster Management and Volunteer Coordination

## 3. Who is the user? (2-3 user types, with roles)

1. **Admin** – Manages disaster events, affected areas, volunteers, relief tasks, resources, and monitors the overall relief operation.

2. **Volunteer** – Registers with skills, location, availability, and experience, accepts suitable relief tasks, updates task progress, and submits completion reports.

3. **Relief Coordinator** – Monitors affected areas, verifies relief requirements, coordinates volunteers and resources, and ensures that high-priority areas receive timely assistance.

## 4. What problem are we solving? (3-5 sentences, real-life example)

During disasters such as floods, cyclones, earthquakes, and other emergencies, managing volunteers, relief tasks, and resources manually can cause delays and confusion. Volunteers may be assigned to tasks without considering their skills, location, availability, and current workload, which can result in inefficient volunteer utilization. Critical affected areas may also face difficulty in receiving required resources on time because resource demand can change rapidly during a disaster. Therefore, a centralized system is needed to coordinate volunteers, prioritize affected areas, assign suitable tasks, track relief activities, and manage resources efficiently.

For example, during a flood, one affected area may require medical volunteers while another area needs food distribution and transportation support. The system can recommend suitable volunteers based on their skills and availability while considering their current workload. It can also analyse relief requirements to help coordinators prepare resources for areas where demand is expected to increase.

## 5. Proposed Solution (what the application will do, feature-wise)

The proposed system is a web-based Volunteer Disaster Relief Coordination System that provides a centralized platform for managing disaster relief activities.

### Core Features

1. **User Registration and Role-Based Login**
   - Provides separate access for Admin, Volunteer, and Relief Coordinator.
   - Volunteers can create profiles with their skills, location, availability, and experience.

2. **Disaster Management**
   - Admin can add, update, view, and manage disaster events.
   - Disaster type, date, description, and status can be maintained.

3. **Affected Area Management**
   - Admin can register affected locations.
   - Population affected and required support can be recorded.
   - Areas can be assigned priority levels.

4. **Relief Task Management**
   - Admin or Relief Coordinator can create relief tasks.
   - Tasks can be assigned to suitable volunteers.
   - Volunteers can accept and update task status.

5. **Task Status Tracking**
   - Task progress can be tracked as:
   - Assigned → Accepted → In Progress → Completed → Verified

6. **Resource Management**
   - Admin can manage available relief resources.
   - Required and available quantities can be tracked.

### Additional Smart Features

7. **Smart Volunteer-Task Matching**
   - The system suggests suitable volunteers based on skills, location, availability, and experience.
   - This feature provides future scope for AI-based volunteer recommendation.

8. **Disaster Priority Scoring**
   - Affected areas are classified as Critical, High, Medium, or Low.
   - Priority is determined using factors such as affected population, severity, and urgency.

9. **Resource Matching**
   - Compares required resources with available resources.
   - Helps identify resource shortages in affected areas.

10. **Duplicate Request Detection**
    - Detects possible duplicate relief requests for the same area and requirement.
    - Helps prevent unnecessary resource allocation.

11. **Emergency SOS Alert**
    - Volunteers can send an SOS alert during emergencies.
    - The system records the volunteer's location and notifies the Admin or Relief Coordinator.

12. **Volunteer Workload Balancing**
    - The system monitors the number of active tasks assigned to each volunteer.
    - When a new task is created, volunteers with suitable skills and lower workloads are given higher priority for recommendation.
    - This prevents overloading a small number of volunteers and improves task distribution.

13. **Relief Demand Forecasting**
    - The system analyses previous and current relief requests, affected population, and resource usage.
    - It estimates which resources may be required more in an affected area.
    - This feature provides future scope for AI-based demand prediction.

14. **Notifications and Reports**
    - Users receive notifications about task assignments, updates, and emergency alerts.
    - Admin and Relief Coordinator can monitor overall relief activities through dashboards and reports.

## 6. Core Entities / Database Tables (list all, minimum 5)

1. **Users**
   - user_id
   - name
   - email
   - password
   - role

2. **Volunteers**
   - volunteer_id
   - user_id
   - skills
   - location
   - availability
   - experience
   - verification_status

3. **Disasters**
   - disaster_id
   - disaster_type
   - disaster_name
   - start_date
   - description
   - status

4. **Affected_Areas**
   - area_id
   - disaster_id
   - location
   - population_affected
   - priority_level
   - required_support

5. **Relief_Tasks**
   - task_id
   - area_id
   - task_name
   - required_skill
   - priority
   - status

6. **Task_Assignments**
   - assignment_id
   - task_id
   - volunteer_id
   - assigned_date
   - accepted_date
   - completion_date

7. **Resources**
   - resource_id
   - resource_name
   - quantity_available
   - resource_type
   - storage_location

8. **Resource_Requests**
   - request_id
   - area_id
   - resource_id
   - quantity_required
   - request_status

9. **SOS_Alerts**
   - alert_id
   - volunteer_id
   - location
   - alert_time
   - alert_status

10. **Relief_Reports**
    - report_id
    - task_id
    - volunteer_id
    - description
    - submitted_date
    - verification_status

11. **Notifications**
    - notification_id
    - user_id
    - message
    - notification_type
    - created_at
    - read_status

## 7. User Roles & Permissions (minimum 2 distinct roles)

### Admin

- Add, update, view, and manage disasters.
- Manage affected areas.
- Manage volunteers.
- Create and assign relief tasks.
- Manage relief resources.
- Verify volunteer information.
- Monitor SOS alerts.
- Monitor task progress.
- View reports and dashboard.

### Volunteer

- Register and login.
- Create and update volunteer profile.
- Add skills, location, availability, and experience.
- View suitable relief tasks.
- Accept or reject assigned tasks.
- Update task progress.
- Submit task completion reports.
- Send SOS alerts.
- Receive notifications.

### Relief Coordinator

- Monitor affected areas.
- Verify relief requirements.
- Coordinate volunteers.
- Monitor resource requirements.
- Track high-priority relief operations.
- Verify completed relief activities.

## 8. Success Criteria (clearly state what you will NOT build)

1. Admin should be able to create, update, view, and manage disaster events.

2. Volunteers should be able to register and maintain their skills, location, availability, and experience.

3. The system should suggest suitable volunteers for relief tasks.

4. The system should consider volunteer workload while recommending volunteers for new tasks.

5. The system should prioritize affected areas based on severity and urgency.

6. Volunteers should be able to accept assigned tasks and update their progress.

7. Admin and Relief Coordinators should be able to monitor task progress from assignment to completion.

8. The system should compare required and available relief resources.

9. The system should identify possible duplicate relief requests.

10. The system should provide SOS alerts for volunteers during emergencies.

11. The system should analyse current and previous relief requirements to estimate future resource demand.

12. The application should provide role-based access for Admin, Volunteer, and Relief Coordinator.

13. The system should store all major information using a relational database.

14. The system should provide dashboards and reports for monitoring disaster relief operations.

15. The project will **not** provide direct medical treatment, physical rescue operations, or emergency transportation services.

16. The project will **not** replace official government emergency response systems.

## 9. Choice of Tech Stack

- **Frontend:** HTML, CSS, JavaScript / React
- **Backend:** Java Spring Boot
- **Database:** MySQL
- **Authentication:** JWT
- **API:** REST API
- **Version Control:** Git and GitHub
- **Cloud Deployment:** AWS / Render
- **Maps & Location:** OpenStreetMap / Google Maps API
- **Notifications:** Email API
- **Testing:** Postman

## 10. Future Trends

1. **AI-Based Volunteer Recommendation**
   - AI can analyse volunteer skills, past performance, location, availability, and task requirements to recommend the most suitable volunteers automatically.

2. **AI-Based Disaster Demand Prediction**
   - Machine learning can analyse historical disaster data, population impact, and previous resource usage to predict future relief resource requirements.

3. **IoT-Based Disaster Monitoring**
   - IoT sensors can provide real-time information such as water levels, temperature, or environmental conditions to help identify high-risk areas.

4. **Real-Time Drone and Satellite Data Integration**
   - Drone or satellite imagery can be integrated to identify damaged areas and improve disaster situation monitoring.

5. **Advanced Real-Time Location Tracking**
   - GPS-based tracking can help coordinators monitor volunteer locations and improve task allocation during large-scale relief operations.

6. **Multi-Language and Voice-Based Assistance**
   - Voice commands and additional regional languages can make the system easier to use during emergency situations.

7. **Predictive Resource Allocation**
   - Future versions can automatically recommend where available resources should be allocated based on predicted demand and disaster priority.