# web
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Student Registration Form</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>

  <div class="container">
    <h1>Student Registration Form</h1>

    <form id="registrationForm">
      
      <!-- Personal Details -->
      <fieldset>
        <legend>Personal Details</legend>
        
        <div class="form-group">
          <label for="fullName">Full Name:</label>
          <input type="text" id="fullName" name="fullName" required>
        </div>

        <div class="form-group">
          <label for="dob">Date of Birth:</label>
          <input type="date" id="dob" name="dob" required>
        </div>

        <div class="form-group">
          <label>Gender:</label>
          <div class="radio-group">
            <label><input type="radio" name="gender" value="Male" required> Male</label>
            <label><input type="radio" name="gender" value="Female"> Female</label>
            <label><input type="radio" name="gender" value="Other"> Other</label>
          </div>
        </div>
      </fieldset>

      <!-- Contact Details -->
      <fieldset>
        <legend>Contact Details</legend>
        
        <div class="form-group">
          <label for="email">Email Address:</label>
          <input type="email" id="email" name="email" required>
        </div>

        <div class="form-group">
          <label for="phone">Phone Number:</label>
          <input type="tel" id="phone" name="phone" required>
        </div>

        <div class="form-group">
          <label for="address">Address:</label>
          <textarea id="address" name="address" rows="3"></textarea>
        </div>
      </fieldset>

      <!-- Academic Details -->
      <fieldset>
        <legend>Academic Details</legend>

        <div class="form-group">
          <label for="course">Course / Major:</label>
          <select id="course" name="course" required>
            <option value="">-- Select Course --</option>
            
            <optgroup label="Computer Science & Technology">
              <option value="Computer Science">Computer Science</option>
              <option value="Information Technology">Information Technology</option>
              <option value="Software Engineering">Software Engineering</option>
              <option value="Cybersecurity">Cybersecurity</option>
              <option value="Data Science & AI">Data Science & AI</option>
              <option value="Web Development">Web Development</option>
            </optgroup>

            <optgroup label="Engineering">
              <option value="Civil Engineering">Civil Engineering</option>
              <option value="Mechanical Engineering">Mechanical Engineering</option>
              <option value="Electrical Engineering">Electrical Engineering</option>
              <option value="Chemical Engineering">Chemical Engineering</option>
              <option value="Aerospace Engineering">Aerospace Engineering</option>
              <option value="Biomedical Engineering">Biomedical Engineering</option>
            </optgroup>

            <optgroup label="Business & Management">
              <option value="Business Administration">Business Administration</option>
              <option value="Accounting">Accounting</option>
              <option value="Finance">Finance</option>
              <option value="Marketing">Marketing</option>
              <option value="Human Resource Management">Human Resource Management</option>
              <option value="International Business">International Business</option>
            </optgroup>

            <optgroup label="Health Sciences & Medicine">
              <option value="Medicine (MBBS)">Medicine (MBBS)</option>
              <option value="Nursing">Nursing</option>
              <option value="Pharmacy">Pharmacy</option>
              <option value="Public Health">Public Health</option>
              <option value="Dentistry">Dentistry</option>
              <option value="Physical Therapy">Physical Therapy</option>
            </optgroup>

            <optgroup label="Natural Sciences & Math">
              <option value="Biology">Biology</option>
              <option value="Chemistry">Chemistry</option>
              <option value="Physics">Physics</option>
              <option value="Mathematics">Mathematics</option>
              <option value="Environmental Science">Environmental Science</option>
            </optgroup>

            <optgroup label="Social Sciences & Humanities">
              <option value="Psychology">Psychology</option>
              <option value="Sociology">Sociology</option>
              <option value="Political Science">Political Science</option>
              <option value="History">History</option>
              <option value="Philosophy">Philosophy</option>
              <option value="Economics">Economics</option>
              <option value="Law / Pre-Law">Law / Pre-Law</option>
            </optgroup>

            <optgroup label="Arts & Media">
              <option value="Graphic Design">Graphic Design</option>
              <option value="Journalism & Mass Media">Journalism & Mass Media</option>
              <option value="Fine Arts">Fine Arts</option>
              <option value="Music & Performing Arts">Music & Performing Arts</option>
              <option value="Architecture">Architecture</option>
            </optgroup>

            <optgroup label="Other Disciplines">
              <option value="Education / Teaching">Education / Teaching</option>
              <option value="Hospitality & Tourism">Hospitality & Tourism</option>
              <option value="Agriculture & Forestry">Agriculture & Forestry</option>
              <option value="Culinary Arts">Culinary Arts</option>
              <option value="Other">Other (Not Listed)</option>
            </optgroup>
          </select>
        </div>

        <div class="form-group">
          <label for="yearLevel">Year Level:</label>
          <select id="yearLevel" name="yearLevel" required>
            <option value="">-- Select Year --</option>
            <option value="1st Year">1st Year</option>
            <option value="2nd Year">2nd Year</option>
            <option value="3rd Year">3rd Year</option>
            <option value="4th Year">4th Year</option>
          </select>
        </div>
      </fieldset>

      <!-- Buttons -->
      <div class="button-group">
        <button type="submit" class="btn btn-submit">Submit Registration</button>
        <button type="reset" class="btn btn-reset">Reset Form</button>
      </div>
    </form>

    <!-- Dynamic Submissions Table -->
    <h2>Registered Students</h2>
    <table id="studentsTable">
      <thead>
        <tr>
          <th>Full Name</th>
          <th>Gender</th>
          <th>Email</th>
          <th>Course</th>
          <th>Year</th>
        </tr>
      </thead>
      <tbody>
      </tbody>
    </table>
  </div>

  <script src="script.js"></script>
</body>
</html>




document.addEventListener("DOMContentLoaded", () => {
  const form = document.getElementById("registrationForm");
  const tableBody = document.querySelector("#studentsTable tbody");

  form.addEventListener("submit", (e) => {
    e.preventDefault(); // Stop page from refreshing on form submit

    // Extract form data
    const fullName = document.getElementById("fullName").value;
    const gender = form.querySelector('input[name="gender"]:checked').value;
    const email = document.getElementById("email").value;
    const course = document.getElementById("course").value;
    const yearLevel = document.getElementById("yearLevel").value;

    // Create a new table row
    const row = document.createElement("tr");
    row.innerHTML = `
      <td>${fullName}</td>
      <td>${gender}</td>
      <td>${email}</td>
      <td>${course}</td>
      <td>${yearLevel}</td>
    `;

    // Append row to table body
    tableBody.appendChild(row);

    // Reset the form input fields
    form.reset();
  });
});









/* Reset and standard box sizing */
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  font-family: Arial, Helvetica, sans-serif;
}

body {
  background-color: #f4f7f6;
  color: #333;
  padding: 20px;
}

.container {
  max-width: 800px;
  margin: 0 auto;
  background: #ffffff;
  padding: 30px;
  border-radius: 8px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
}

h1, h2 {
  text-align: center;
  color: #2c3e50;
  margin-bottom: 20px;
}

fieldset {
  border: 1px solid #cccccc;
  border-radius: 6px;
  padding: 15px 20px;
  margin-bottom: 20px;
}

legend {
  font-weight: bold;
  color: #2c3e50;
  padding: 0 8px;
}

.form-group {
  margin-bottom: 15px;
}

.form-group label {
  display: block;
  margin-bottom: 6px;
  font-weight: 600;
}

input[type="text"],
input[type="date"],
input[type="email"],
input[type="tel"],
select,
textarea {
  width: 100%;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 4px;
  font-size: 14px;
}

input:focus,
select:focus,
textarea:focus {
  outline: none;
  border-color: #3498db;
}

.radio-group label {
  display: inline-block;
  margin-right: 15px;
  font-weight: normal;
}

.button-group {
  display: flex;
  gap: 10px;
  margin-bottom: 30px;
}

.btn {
  flex: 1;
  padding: 12px;
  border: none;
  border-radius: 4px;
  font-size: 16px;
  cursor: pointer;
  transition: background 0.2s;
}

.btn-submit {
  background-color: #2ecc71;
  color: white;
}

.btn-submit:hover {
  background-color: #27ae60;
}

.btn-reset {
  background-color: #e74c3c;
  color: white;
}

.btn-reset:hover {
  background-color: #c0392b;
}

/* Table styles */
table {
  width: 100%;
  border-collapse: collapse;
  margin-top: 15px;
}

th, td {
  border: 1px solid #dddddd;
  padding: 10px;
  text-align: left;
}

th {
  background-color: #34495e;
  color: white;
}

tr:nth-child(even) {
  background-color: #f9f9f9;
}
