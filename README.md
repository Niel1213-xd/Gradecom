<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>BSIT Grade Calculator</title>

<style>
* {
    box-sizing: border-box;
}

body {
    margin: 0;
    padding: 30px 16px;
    font-family: Arial, sans-serif;
    background: linear-gradient(135deg, #2c2a2a, #313132);
    color: #1e293b;
}

header {
    text-align: center;
    margin-bottom: 30px;
}

.logo {
    font-size: 42px;
}

h1 {
    font-size: 34px;
    margin: 10px 0;
    color:crimson
}

h1 span {
    color: #ecebf2;
}

header p {
    color: #fefcfc;
}

.container {
    max-width: 1100px;
    margin: auto;
    display: grid;
    grid-template-columns: 1.2fr 0.8fr;
    gap: 22px;
    align-items: start;
}

.card {
    padding: 25px;
    border-radius: 22px;
    background: white;
    box-shadow: 0 12px 35px #435b971c;
}

h2 {
    font-size: 20px;
    margin: 0 0 20px;
}

label {
    display: block;
    font-size: 13px;
    font-weight: bold;
    margin: 15px 0 7px;
}

input {
    width: 100%;
    padding: 12px;
    border: 1px solid #d6dfef;
    border-radius: 10px;
    font-size: 14px;
    outline: none;
    background: rgb(241, 241, 244);
}

input:focus {
    border-color: #0a0909;
    box-shadow: 0 0 0 3px #7955f51a;
}

.name-field {
    margin-bottom: 25px;
}

.subject-heading,
.subject {
    display: grid;
    grid-template-columns: minmax(0, 1fr) 80px 80px;
    gap: 8px;
    align-items: center;
}

.subject-heading {
    padding: 0 10px;
    margin-bottom: 10px;
    font-size: 11px;
    color: #64748b;
    font-weight: bold;
    text-align: center;
}

.subject-heading span:first-child {
    text-align: left;
}

.subject {
    padding: 12px 10px;
    border-radius: 12px;
    margin-bottom: 10px;
}

.subject-name {
    font-size: 13px;
    font-weight: bold;
    line-height: 1.4;
}

.subject input {
    padding: 11px 3px;
    text-align: center;
    font-size: 13px;
}

.blue { background: #eff6ff; }
.purple { background: #f3efff; }
.green { background: #eafaf1; }
.orange { background: #fff3e9; }
.pink { background: #fff0f5; }
.yellow { background: #fff9df; }
.cyan { background: #e9faff; }
.gray { background: #f1f5f9; }

.buttons {
    display: flex;
    gap: 10px;
    margin-top: 22px;
}

button {
    border: none;
    padding: 14px;
    border-radius: 11px;
    font-weight: bold;
    font-size: 14px;
    cursor: pointer;
}

.compute {
    flex: 2;
    color: white;
    background: linear-gradient(100deg, #159bf4, #8951f5);
}

.clear {
    flex: 1;
    color: #344563;
    background: #edf1f8;
}

button:hover {
    opacity: 0.9;
}

#notice {
    color: #dc3545;
    font-size: 13px;
    line-height: 1.5;
}

.result {
    color: white;
    background: linear-gradient(150deg, #24558c, #122541);
}

.circle {
    width: 150px;
    height: 150px;
    border: 7px solid #43d5a0;
    border-radius: 50%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    margin: 0 auto 20px;
}

.circle strong {
    font-size: 35px;
}

.circle small {
    margin-top: 5px;
    color: #d7e4f7;
    font-size: 11px;
}

.status {
    display: table;
    margin: 0 auto 22px;
    background: #475569;
    border-radius: 25px;
    padding: 10px 20px;
    font-size: 12px;
    font-weight: bold;
}

.student {
    border-top: 1px solid #ffffff33;
    border-bottom: 1px solid #ffffff33;
    padding: 17px 0;
    margin-bottom: 12px;
}

.muted {
    font-size: 12px;
    color: #b9cce6;
    margin-bottom: 7px;
}

#studentName {
    font-weight: bold;
    overflow-wrap: anywhere;
}

.row {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 10px;
    padding: 10px 0;
    font-size: 12px;
}

.row strong {
    text-align: right;
    white-space: nowrap;
}

.total {
    border-top: 1px solid #ffffff33;
    margin-top: 10px;
    padding-top: 12px;
}

.message {
    text-align: center;
    background: #ffffff12;
    border-radius: 12px;
    padding: 13px;
    margin-top: 20px;
    font-size: 13px;
    line-height: 1.5;
}

.scale {
    margin-top: 22px;
}

.scale summary {
    cursor: pointer;
    font-weight: bold;
    font-size: 14px;
}

.scale table {
    width: 100%;
    border-collapse: collapse;
    margin-top: 12px;
    font-size: 12px;
}

.scale th,
.scale td {
    padding: 9px 5px;
    text-align: left;
    border-bottom: 1px solid #e5e7eb;
}

.scale td:last-child,
.scale th:last-child {
    text-align: right;
}

.note {
    font-size: 12px;
    line-height: 1.5;
    color: #64748b;
}

@media (max-width: 760px) {
    body {
        padding: 20px 10px;
    }

    .container {
        grid-template-columns: 1fr;
    }

    .card {
        padding: 20px 12px;
    }

    h1 {
        font-size: 28px;
    }

    .subject-heading,
    .subject {
        grid-template-columns: minmax(0, 1fr) 68px 68px;
        gap: 5px;
        padding-left: 6px;
        padding-right: 6px;
    }

    .subject-name {
        font-size: 12px;
    }
}
</style>
</head>

<body>

<header>
    
    <h1>BSIT <span>Grade Calculator</span></h1>
    <p>First Year College · Midterm & Final Grades</p>
</header>

<main class="container">

<section class="card">
    <h2>👤 Student Information</h2>

    <div class="name-field">
        <label for="student">Student Name</label>
        <input id="student" type="text"
               placeholder="Enter your full name">
    </div>

    <h2>📚 Courses</h2>

    <div class="subject-heading">
        <span>SUBJECT</span>
        <span>MIDTERM</span>
        <span>FINAL</span>
    </div>

    <div class="subject blue">
        <span class="subject-name"> IT Fundamentals</span>
        <input id="mid0" type="number" min="1" max="5"
               step="0.25" placeholder="1.25">
        <input id="fin0" type="number" min="1" max="5"
               step="0.25" placeholder="1.75">
    </div>

    <div class="subject purple">
        <span class="subject-name"> Understanding the Self</span>
        <input id="mid1" type="number" min="1" max="5"
               step="0.25" placeholder="1.25">
        <input id="fin1" type="number" min="1" max="5"
               step="0.25" placeholder="1.75">
    </div>

    <div class="subject green">
        <span class="subject-name"> Programming 1</span>
        <input id="mid2" type="number" min="1" max="5"
               step="0.25" placeholder="1.25">
        <input id="fin2" type="number" min="1" max="5"
               step="0.25" placeholder="1.75">
    </div>

    <div class="subject orange">
        <span class="subject-name"> Discrete Structure</span>
        <input id="mid3" type="number" min="1" max="5"
               step="0.25" placeholder="1.25">
        <input id="fin3" type="number" min="1" max="5"
               step="0.25" placeholder="1.75">
    </div>

    <div class="subject pink">
        <span class="subject-name"> Math in the Modern World</span>
        <input id="mid4" type="number" min="1" max="5"
               step="0.25" placeholder="1.25">
        <input id="fin4" type="number" min="1" max="5"
               step="0.25" placeholder="1.75">
    </div>

    <div class="subject yellow">
        <span class="subject-name"> Fil 1</span>
        <input id="mid5" type="number" min="1" max="5"
               step="0.25" placeholder="1.25">
        <input id="fin5" type="number" min="1" max="5"
               step="0.25" placeholder="1.75">
    </div>

    <div class="subject cyan">
        <span class="subject-name"> NSTP 1</span>
        <input id="mid6" type="number" min="1" max="5"
               step="0.25" placeholder="1.25">
        <input id="fin6" type="number" min="1" max="5"
               step="0.25" placeholder="1.75">
    </div>

    <div class="subject gray">
        <span class="subject-name"> PATHFIT 1</span>
        <input id="mid7" type="number" min="1" max="5"
               step="0.25" placeholder="1.25">
        <input id="fin7" type="number" min="1" max="5"
               step="0.25" placeholder="1.75">
    </div>

    <div class="buttons">
        <button class="compute" onclick="computeGrades()">
             Compute Grades
        </button>
        <button class="clear" onclick="clearForm()">
             Clear
        </button>
    </div>

    <p id="notice" role="alert"></p>

    <details class="scale">
        <summary>📊 Grade Equivalent Guide</summary>

        <table>
            <thead>
                <tr>
                    <th>Percentage</th>
                    <th>Equivalent</th>
                </tr>
            </thead>
            <tbody>
                <tr><td>97–100%</td><td>1.00</td></tr>
                <tr><td>94–96%</td><td>1.25</td></tr>
                <tr><td>91–93%</td><td>1.50</td></tr>
                <tr><td>88–90%</td><td>1.75</td></tr>
                <tr><td>85–87%</td><td>2.00</td></tr>
                <tr><td>82–84%</td><td>2.25</td></tr>
                <tr><td>79–81%</td><td>2.50</td></tr>
                <tr><td>76–78%</td><td>2.75</td></tr>
                <tr><td>75%</td><td>3.00</td></tr>
                <tr><td>Below 75%</td><td>5.00</td></tr>
            </tbody>
        </table>

        <p class="note">
            Enter the grade equivalent you received for each exam.
            The semester grade is the average of Midterm and Final.
        </p>
    </details>
</section>

<section class="card result">
    <h2>       First Semester Results</h2>

    <div class="circle">
        <strong id="average">--.--</strong>
        <small>Overall Grade</small>
    </div>

    <div class="status" id="status">AWAITING GRADES</div>

    <div class="student">
        <div class="muted">👤 STUDENT</div>
        <div id="studentName">Your name will appear here</div>
    </div>

    <div id="subjectResults">
        <div class="row"><span>IT Fundamentals</span><strong>--</strong></div>
        <div class="row"><span>Understanding the Self</span><strong>--</strong></div>
        <div class="row"><span>Programming 1</span><strong>--</strong></div>
        <div class="row"><span>Discrete Structure</span><strong>--</strong></div>
        <div class="row"><span>Math in the Modern World</span><strong>--</strong></div>
        <div class="row"><span>Filipino 1</span><strong>--</strong></div>
        <div class="row"><span>NSTP 1</span><strong>--</strong></div>
        <div class="row"><span>PATHFIT 1</span><strong>--</strong></div>
    </div>

    <div class="total">
        <div class="row">
            <span>∑ Total of Subject Grades</span>
            <strong id="total">--</strong>
        </div>

        <div class="row">
            <span>📊 Overall Average</span>
            <strong id="average2">--.--</strong>
        </div>

        <div class="row">
            <span>🎓 Overall Standing</span>
            <strong id="standing">--</strong>
        </div>
    </div>

    <div class="message" id="message">
         Enter your grades to calculate your First Semester Grade.
    </div>
</section>

</main>

<script>
const subjects = [
    "IT Fundamentals",
    "Understanding the Self",
    "Programming 1",
    "Discrete Structure",
    "Math in the Modern World",
    "Filipino 1",
    "NSTP 1",
    "PATHFIT 1"
];

function validGrade(value) {
    // Accept only the grade equivalents listed in the guide.
    const allowed = [
        1, 1.25, 1.5, 1.75, 2, 2.25,
        2.5, 2.75, 3, 5
    ];

    return allowed.some(grade => grade === Number(value));
}

function computeGrades() {
    const name = document.getElementById("student").value.trim();
    const notice = document.getElementById("notice");
    const semesterGrades = [];

    notice.textContent = "";

    if (!name) {
        notice.textContent = "Please enter the student's name.";
        document.getElementById("student").focus();
        return;
    }

    for (let i = 0; i < subjects.length; i++) {
        const mid = document.getElementById("mid" + i).value;
        const fin = document.getElementById("fin" + i).value;

        if (mid === "" || fin === "") {
            notice.textContent =
                "Please enter both Midterm and Final grades for all subjects.";
            return;
        }

        if (!validGrade(mid) || !validGrade(fin)) {
            notice.textContent =
                "Use only valid grade equivalents: 1.00, 1.25, 1.50, 1.75, 2.00, 2.25, 2.50, 2.75, 3.00, or 5.00.";
            return;
        }

        // Average the Midterm and Final grade equivalents.
        const semesterGrade = (Number(mid) + Number(fin)) / 2;
        semesterGrades.push(semesterGrade);
    }

    const total = semesterGrades.reduce(
        (sum, grade) => sum + grade, 0
    );

    const average = total / semesterGrades.length;

    document.getElementById("studentName").textContent = name;
    document.getElementById("average").textContent = average.toFixed(3);
    document.getElementById("average2").textContent = average.toFixed(3);
    document.getElementById("total").textContent = total.toFixed(2);

    // Lower numerical equivalents are better.
    const passed = semesterGrades.every(grade => grade <= 3);

    const status = document.getElementById("status");
    status.textContent = passed ? "✓ ALL SUBJECTS PASSED" : "✕ FAILED SUBJECT";
    status.style.background = passed ? "#20a879" : "#df435b";

    document.getElementById("subjectResults").innerHTML =
        subjects.map((subject, i) => {
            return `
                <div class="row">
                    <span>${subject}</span>
                    <strong>${semesterGrades[i].toFixed(3)}</strong>
                </div>
            `;
        }).join("");

    document.getElementById("standing").textContent =
        passed ? "PASSED" : "WITH 5.00 GRADE";

    document.getElementById("message").textContent = passed
        ? " Congratulations! You passed all your subjects!"
        : " You have a subject with a failing grade. Keep going!";
}

function clearForm() {
    document.getElementById("student").value = "";

    for (let i = 0; i < subjects.length; i++) {
        document.getElementById("mid" + i).value = "";
        document.getElementById("fin" + i).value = "";
    }

    document.getElementById("average").textContent = "--.--";
    document.getElementById("average2").textContent = "--.--";
    document.getElementById("total").textContent = "--";
    document.getElementById("standing").textContent = "--";
    document.getElementById("studentName").textContent =
        "Your name will appear here";

    const status = document.getElementById("status");
    status.textContent = "AWAITING GRADES";
    status.style.background = "#475569";

    document.getElementById("notice").textContent = "";
    document.getElementById("message").textContent =
        " Enter your grades to calculate your First Semester Grade!";

    document.getElementById("subjectResults").innerHTML =
        subjects.map(subject => `
            <div class="row">
                <span>${subject}</span>
                <strong>--</strong>
            </div>
        `).join("");
}
</script>

</body>
</html>
