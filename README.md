<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>জীবন বিজ্ঞান কুইজ - অধ্যায় ৫ (সেট ৬ - ১০ মিনিট)</title>
    <style>
        :root {
            --primary-color: #27ae60;
            --primary-hover: #1e8449;
            --bg-color: #f4f9f4;
            --text-color: #2c3e50;
            --card-bg: #ffffff;
            --correct-color: #2ecc71;
            --wrong-color: #e74c3c;
            --timer-color: #d35400;
            --admin-color: #8e44ad;
            --next-set-color: #2980b9;
            --next-set-hover: #3498db;
        }

        body {
            font-family: 'Segoe UI', Arial, sans-serif;
            background-color: var(--bg-color);
            color: var(--text-color);
            margin: 0;
            padding: 20px;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
        }

        .container {
            background-color: var(--card-bg);
            width: 100%;
            max-width: 800px;
            padding: 40px 30px;
            border-radius: 12px;
            box-shadow: 0 10px 30px rgba(39, 174, 96, 0.08);
            position: relative;
            height: fit-content;
        }

        h1 {
            text-align: center;
            color: var(--primary-hover);
            margin-bottom: 5px;
            font-size: 1.8em;
        }

        .subtitle {
            text-align: center;
            color: #7f8c8d;
            margin-bottom: 25px;
            font-size: 1em;
        }

        /* Login Section Styles */
        #login-section {
            display: block;
            max-width: 400px;
            margin: 0 auto;
        }

        .form-group {
            margin-bottom: 20px;
        }

        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: bold;
            color: #555;
        }

        .form-group input {
            width: 100%;
            padding: 12px 15px;
            border: 2px solid #e9ecef;
            border-radius: 8px;
            font-size: 1.1em;
            box-sizing: border-box;
            transition: border-color 0.3s ease;
        }

        .form-group input:focus {
            border-color: var(--primary-color);
            outline: none;
        }

        .error-message {
            color: var(--wrong-color);
            text-align: center;
            font-weight: bold;
            margin-bottom: 15px;
            display: none;
        }

        /* Quiz, Admin & Limit Block Sections */
        #quiz-section, #admin-section, #limit-section {
            display: none;
        }

        .limit-box {
            text-align: center;
            padding: 30px;
            background-color: #fce4d6;
            border: 2px solid #f1948a;
            border-radius: 8px;
            color: #c0392b;
            font-size: 1.2em;
            font-weight: bold;
            margin-bottom: 20px;
        }

        .question-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
            font-weight: bold;
            color: #7f8c8d;
        }

        .timer-box {
            background-color: #fdf2e9;
            color: var(--timer-color);
            padding: 6px 15px;
            border-radius: 20px;
            border: 1px solid #fadbd8;
            font-size: 1.1em;
            display: flex;
            align-items: center;
            gap: 5px;
        }

        .question-text {
            font-size: 1.25em;
            font-weight: 600;
            margin-bottom: 20px;
            line-height: 1.5;
        }

        .options-list {
            list-style: none;
            padding: 0;
            margin: 0;
        }

        .option-item {
            background-color: #f8f9fa;
            border: 2px solid #e9ecef;
            border-radius: 8px;
            padding: 15px 20px;
            margin-bottom: 12px;
            font-size: 1.1em;
            cursor: pointer;
            transition: all 0.2s ease;
        }

        .option-item:hover {
            border-color: var(--primary-color);
            background-color: #f4fbf6;
        }

        .option-item.selected {
            background-color: var(--primary-color);
            color: white;
            border-color: var(--primary-color);
        }

        .btn {
            background-color: var(--primary-color);
            color: white;
            border: none;
            padding: 15px 30px;
            font-size: 1.1em;
            font-weight: bold;
            border-radius: 8px;
            cursor: pointer;
            width: 100%;
            margin-top: 10px;
            transition: background-color 0.3s ease;
        }

        .btn:hover {
            background-color: var(--primary-hover);
        }

        /* Next Set Link Button */
        .btn-next-set {
            background-color: var(--next-set-color);
            text-align: center;
            text-decoration: none;
            display: block;
            box-sizing: border-box;
            font-size: 1.1em;
            font-weight: bold;
            color: white;
            padding: 15px 30px;
            border-radius: 8px;
            margin-top: 10px;
            transition: background-color 0.3s ease;
        }

        .btn-next-set:hover {
            background-color: var(--next-set-hover);
        }

        /* Admin Dashboard Table */
        .admin-title {
            color: var(--admin-color) !important;
        }
        
        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 20px;
            font-size: 1.05em;
        }

        th, td {
            border: 1px solid #e2e8f0;
            padding: 12px 15px;
            text-align: left;
        }

        th {
            background-color: #f1f5f9;
            color: #334155;
            font-weight: bold;
        }

        tr:nth-child(even) {
            background-color: #f8fafc;
        }

        /* Results Display */
        #result-section {
            display: none;
        }

        .score-board {
            text-align: center;
            padding: 20px;
            background: linear-gradient(135deg, #eaf2e8, #d5ebd5);
            border-radius: 10px;
            margin-bottom: 20px;
        }

        .score-board h2 {
            margin: 0;
            color: #2c3e50;
            font-size: 1.8em;
        }

        .review-item {
            background-color: #fdfdfd;
            border: 1px solid #e0e0e0;
            border-radius: 8px;
            padding: 20px;
            margin-bottom: 20px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.02);
        }

        .review-q {
            font-size: 1.1em;
            font-weight: bold;
            margin-bottom: 15px;
        }

        .review-ans {
            margin-bottom: 8px;
            font-size: 1em;
        }

        .ans-correct { color: var(--correct-color); font-weight: bold; }
        .ans-wrong { color: var(--wrong-color); font-weight: bold; }

        .explanation {
            background-color: #fff9e6;
            border-left: 4px solid #f1c40f;
            padding: 12px 15px;
            margin-top: 15px;
            font-size: 0.95em;
            color: #555;
            border-radius: 0 4px 4px 0;
        }

        .welcome-text {
            color: var(--primary-hover);
            font-weight: bold;
        }
    </style>
</head>
<body>

<div class="container">

    <!-- Login Section -->
    <div id="login-section">
        <h1>স্টুডেন্ট ও অ্যাডমিন লগইন</h1>
        <p class="subtitle">জীবন বিজ্ঞান প্র্যাকটিস সেট শুরু করতে নিচে লগইন করুন</p>

        <div class="form-group">
            <label for="username">ইউজারনেম (Username)</label>
            <input type="text" id="username" placeholder="আপনার ইউজারনেম দিন" autocomplete="off">
        </div>

        <div class="form-group">
            <label for="password">পাসওয়ার্ড (Password)</label>
            <input type="password" id="password" placeholder="আপনার গোপন পাসওয়ার্ড দিন">
        </div>

        <div class="error-message" id="error-message">ইউজারনেম অথবা পাসওয়ার্ড ভুল হয়েছে!</div>

        <button class="btn" id="login-btn">লগইন করুন</button>
    </div>

    <!-- Attempt Limit Exceeded Section -->
    <div id="limit-section">
        <div class="limit-box">
            ⚠️ দুঃখিত, আপনার এই সেটের জন্য নির্ধারিত ১০ বার পরীক্ষার লিমিট শেষ হয়ে গেছে!
        </div>
        <p style="text-align: center; color: #555;">আপনি আর নতুন করে এই কুইজটিতে অংশগ্রহণ করতে পারবেন না। পরবর্তী সুযোগের জন্য আপনার শিক্ষকের সাথে যোগাযোগ করুন।</p>
        <button class="btn" onclick="location.reload()">লগ আউট ও ফিরে যান</button>
    </div>

    <!-- Admin Panel Section -->
    <div id="admin-section">
        <h1 class="admin-title">📊 শিক্ষক ড্যাশবোর্ড (Admin Panel)</h1>
        <p class="subtitle">পরীক্ষার্থীদের লাইভ পারফরম্যান্স ও মক টেস্টের ফুল রিপোর্ট (সর্বোচ্চ ১০ বার লিমিট)</p>
        
        <table>
            <thead>
                <tr>
                    <th>ছাত্রের নাম (Username)</th>
                    <th>সর্বোচ্চ স্কোর (Best Score)</th>
                    <th>মোট কতবার দিয়েছে (Total Attempts)</th>
                    <th>স্ট্যাটাস (Status)</th>
                </tr>
            </thead>
            <tbody id="admin-table-body">
                <!-- Data injected via JS -->
            </tbody>
        </table>
        
        <button class="btn" style="background-color: var(--admin-color); margin-top: 30px;" onclick="clearReports()">সমস্ত রেকর্ড ও লিমিট রিসেট করুন</button>
        <button class="btn" onclick="location.reload()">লগ আউট করুন</button>
    </div>

    <!-- Quiz Section -->
    <div id="quiz-section">
        <h1>জীবন বিজ্ঞান কুইজ: অধ্যায় ৫</h1>
        <div class="subtitle">
            <span class="welcome-text">পরীক্ষার্থী: <span id="student-name"></span></span> | সেট ৬: জীববৈচিত্র্যের ধারণা, গুরুত্ব এবং হটস্পট
        </div>

        <div class="question-header">
            <span id="q-counter">প্রশ্ন: ১ / ১৫</span>
            <div class="timer-box">
                ⏱️ সময় বাকি: <span id="timer-display">10:00</span>
            </div>
        </div>

        <div class="question-text" id="question-text">এখানে প্রশ্ন আসবে</div>
        <ul class="options-list" id="options-list">
            <!-- Options via JS -->
        </ul>

        <button class="btn" id="next-btn">পরবর্তী প্রশ্ন</button>
    </div>

    <!-- Result Section -->
    <div id="result-section">
        <div class="score-board">
            <h2>পরীক্ষা সম্পন্ন হয়েছে, <span id="result-student-name"></span>!</h2>
            <h1 style="margin-top: 10px;" id="final-score">স্কোর: 0 / 15</h1>
        </div>

        <!-- Set 7 Real Link Added Here -->
        <a href="https://tetsbazar.github.io/Class-10-Life-Science-Chapter-5-set-7-/" target="_blank" class="btn-next-set">
            👉 পরবর্তী মক টেস্ট (সেট - ৭) দেওয়ার জন্য এখানে ক্লিক করুন
        </a>

        <h3 style="margin-top: 30px;">প্রশ্নের বিস্তারিত পর্যালোচনা:</h3>
        <div id="review-container">
            <!-- Review items via JS -->
        </div>
        <button class="btn" onclick="location.reload()">লগ আউট করুন</button>
    </div>

</div>

<script>
    // --- Login System Database ---
    const approvedStudents = {
        "anil7890": "12345677",
        "samir7890": "12345666",
        "rahul2024": "pass1234",
        "rohit999": "88889999",
        "suman007": "abcdef12",
        "Dhiren": "Dhiren1234",
        "Pradip": "Pradip1234",
        "Bijay": "Bijay1234",
        "admin": "admin1234" 
    };

    const attemptLimit = 10; // Maximum allowed exam attempts per student

    const loginSection = document.getElementById("login-section");
    const quizSection = document.getElementById("quiz-section");
    const adminSection = document.getElementById("admin-section");
    const limitSection = document.getElementById("limit-section");
    const adminTableBody = document.getElementById("admin-table-body");
    const usernameInput = document.getElementById("username");
    const passwordInput = document.getElementById("password");
    const loginBtn = document.getElementById("login-btn");
    const errorMessage = document.getElementById("error-message");
    const studentNameDisplay = document.getElementById("student-name");
    const resultStudentName = document.getElementById("result-student-name");

    let currentUsername = "";

    loginBtn.addEventListener("click", () => {
        const username = usernameInput.value.trim();
        const password = passwordInput.value.trim();

        if (approvedStudents[username] && approvedStudents[username] === password) {
            errorMessage.style.display = "none";
            loginSection.style.display = "none";
            currentUsername = username;

            if (username === "admin") {
                adminSection.style.display = "block";
                loadAdminData();
            } else {
                // Check Attempt Limit before starting
                const userReport = JSON.parse(localStorage.getItem(`quiz_report_ch5_s6_${currentUsername}`)) || { bestScore: 0, attempts: 0 };
                
                if (userReport.attempts >= attemptLimit) {
                    limitSection.style.display = "block";
                } else {
                    quizSection.style.display = "block";
                    studentNameDisplay.innerText = username;
                    resultStudentName.innerText = username;

                    loadQuestion();
                    startTimer(10 * 60); // 10 Minutes Timer
                }
            }
        } else {
            errorMessage.style.display = "block";
        }
    });

    // --- Admin Dashboard Storage ---
    function loadAdminData() {
        adminTableBody.innerHTML = "";
        Object.keys(approvedStudents).forEach(user => {
            if (user !== "admin") {
                const userReport = JSON.parse(localStorage.getItem(`quiz_report_ch5_s6_${user}`)) || { bestScore: "পরীক্ষা দেয়নি", attempts: 0 };
                
                let statusText = "চলমান";
                let statusColor = "#27ae60";
                if (userReport.attempts >= attemptLimit) {
                    statusText = "লকড (সীমা শেষ)";
                    statusColor = "var(--wrong-color)";
                } else if (userReport.attempts === 0) {
                    statusText = "অংশগ্রহণ করেনি";
                    statusColor = "#7f8c8d";
                }

                const row = document.createElement("tr");
                row.innerHTML = `
                    <td><strong>${user}</strong></td>
                    <td style="color: ${typeof userReport.bestScore === 'number' ? 'var(--primary-color)' : '#7f8c8d'}; font-weight: bold;">
                        ${typeof userReport.bestScore === 'number' ? userReport.bestScore + ' / 15' : userReport.bestScore}
                    </td>
                    <td><span style="background: #e2e8f0; padding: 3px 10px; border-radius: 10px; font-weight: bold;">${userReport.attempts} / ${attemptLimit} বার</span></td>
                    <td style="color: ${statusColor}; font-weight: bold;">${statusText}</td>
                `;
                adminTableBody.appendChild(row);
            }
        });
    }

    function clearReports() {
        if (confirm("আপনি কি নিশ্চিতভাবে সমস্ত ছাত্র-ছাত্রীর পরীক্ষার রেকর্ড ও অ্যাটেম্পট হিস্ট্রি ডিলিট করে লিমিট নতুন করে রিসেট করতে চান?")) {
            Object.keys(approvedStudents).forEach(user => {
                if (user !== "admin") {
                    localStorage.removeItem(`quiz_report_ch5_s6_${user}`);
                }
            });
            loadAdminData();
            alert("সমস্ত ডাটা এবং পরীক্ষার লিমিট সফলভাবে রিসেট করা হয়েছে।");
        }
    }

    // --- Life Science Chapter 5 Set 6 Question Data Bank ---
    const quizData = [
        {
            question: "১. 'Biodiversity' বা জীববৈচিত্র্য শব্দটি ১৯৮৫ খ্রিস্টাব্দে প্রথম কে প্রবর্তন করেন?",
            options: ["নরম্যান মায়ার্স", "ডব্লিউ. জি. রোজেন (W. G. Rosen)", "চার্লস ডারউইন", "জ্যাঁ ব্যাপটিস্ট ল্যামার্ক"],
            answer: "ডব্লিউ. জি. রোজেন (W. G. Rosen)",
            explanation: "বিজ্ঞানি ডব্লিউ. জি. রোজেন প্রথম জীবজগতের এই বৈচিত্র্য বোঝাতে 'বায়োডাইভার্সিটি' শব্দটি ব্যবহার করেন।"
        },
        {
            question: "২. কোনো বিস্তীর্ণ অঞ্চলে বিভিন্ন বাস্তুতন্ত্রের রূপভেদে সৃষ্ট বৈচিত্র্যকে কী বলে?",
            options: ["জিনগত বৈচিত্র্য", "প্রজাতিগত বৈচিত্র্য", "বাস্তুতান্ত্রিক বৈচিত্র্য", "মহাজাগতিক বৈচিত্র্য"],
            answer: "বাস্তুতান্ত্রিক বৈচিত্র্য",
            explanation: "জীববৈচিত্র্য প্রধানত তিন প্রকারের হয়— জিনগত, প্রজাতিগত এবং বাস্তুতান্ত্রিক।"
        },
        {
            question: "৩. ম্যালেরিয়া রোগের ওষুধ 'কুইনাইন' এবং ক্যানসারের চিকিৎসায় ব্যবহৃত 'ট্যাক্সল' কোথা থেকে পাওয়া যায়?",
            options: ["সমুদ্রের জল থেকে", "রাসায়নিক কারখানা থেকে", "উদ্ভিদ থেকে (জীববৈচিত্র্যের অবদান)", "প্রাণীর দেহ থেকে"],
            answer: "উদ্ভিদ থেকে (জীববৈচিত্র্যের অবদান)",
            explanation: "জীববৈচিত্র্যের অন্যতম বড়ো গুরুত্ব হলো এটি আমাদের জীবনদায়ী ওষুধের জোগান দেয়। সিঙ্কোনা গাছের ছাল থেকে কুইনাইন পাওয়া যায়।"
        },
        {
            question: "৪. পৃথিবীর কোনো কোনো স্থানে অত্যধিক সংখ্যায় জীব প্রজাতি বসবাস করে যা আজ বিপন্ন। এই অঞ্চলগুলোকে 'হটস্পট' (Hotspots) কে আখ্যা দেন?",
            options: ["ডব্লিউ. জি. রোজেন", "নরম্যান মায়ার্স (Norman Myers)", "ওপারিন", "মেন্ডেল"],
            answer: "নরম্যান মায়ার্স (Norman Myers)",
            explanation: "বিজ্ঞানি নরম্যান মায়ার্স ১৯৮৮ সালে এই অতি-বৈচিত্র্যময় কিন্তু বিপন্ন অঞ্চলগুলোকে বাঁচানোর জন্য প্রথম 'হটস্পট' ধারণার প্রবর্তন করেন।"
        },
        {
            question: "৫. কোনো অঞ্চলকে 'বায়োডাইভার্সিটি হটস্পট' হিসেবে ঘোষণা করতে হলে প্রধান শর্ত কী?",
            options: ["সেখানে অন্তত ১৫০০ প্রজাতির এনডেমিক উদ্ভিদ থাকতে হবে", "ওই অঞ্চলের প্রাথমিক উদ্ভিদ সম্প্রদায়ের কমপক্ষে ৭০ শতাংশ অবলুপ্ত হতে হবে", "সেখানে কোনো মানুষ থাকা চলবে না", "ক এবং খ উভয়ই"],
            answer: "ক এবং খ উভয়ই",
            explanation: "হটস্পট হতে গেলে সেখানে নিজস্ব বা এনডেমিক প্রজাতির আধিক্য থাকতে হবে এবং অঞ্চলটিকে ধ্বংসের চরম মাত্রায় থাকতে হবে।"
        },
        {
            question: "৬. বর্তমানে পৃথিবীতে মোট কতগুলি জীববৈচিত্র্য হটস্পট রয়েছে?",
            options: ["৪টি", "১৮টি", "৩৬টি", "৫২টি"],
            answer: "৩৬টি",
            explanation: "সারা বিশ্বে বর্তমানে ৩৬টি হটস্পট চিহ্নিত করা হয়েছে, যার মধ্যে ভারতের ৪টি হটস্পট রয়েছে।"
        },
        {
            question: "৭. নিচের কোনটি ভারতের একটি জীববৈচিত্র্য হটস্পট?",
            options: ["থর মরুভূমি", "ছোটনাগপুর মালভূমি", "পূর্ব হিমালয়", "আরাবল্লী পর্বত"],
            answer: "পূর্ব হিমালয়",
            explanation: "ভারতের ৪টি হটস্পট হলো— পূর্ব হিমালয়, ইন্দো-বার্মা, পশ্চিমঘাট ও শ্রীলঙ্কা এবং সুন্দাল্যান্ড।"
        },
        {
            question: "৮. ভারতের কোন হটস্পট অঞ্চলে 'লায়ন-টেল্ড ম্যাকাক' (Lion-tailed macaque) নামক বিপন্ন বানর প্রজাতি দেখা যায়?",
            options: ["সুন্দাল্যান্ড", "পূর্ব হিমালয়", "পশ্চিমঘাট ও শ্রীলঙ্কা", "indo-বার্মা"],
            answer: "পশ্চিমঘাট ও শ্রীলঙ্কা",
            explanation: "ভারতের গুজরাট, কর্ণাটক, কেরল থেকে শ্রীলঙ্কা পর্যন্ত বিস্তৃত এই হটস্পটে এই বিশেষ প্রজাতির বানর পাওয়া যায়।"
        },
        {
            question: "৯. ভারতের কোন হটস্পটে কলসপত্রী উদ্ভিদ এবং 'গোল্ডেন লেঙ্গুর' দেখা যায়?",
            options: ["পশ্চিমঘাট পর্বতমালা", "পূর্ব হিমালয়", "সুন্দাল্যান্ড", "ইন্দো-বার্মা"],
            answer: "পূর্ব হিমালয়",
            explanation: "সিকিম, আসাম, অরুণাচল নিয়ে গঠিত পূর্ব হিমালয় হটস্পটে এরা বাস করে।"
        },
        {
            question: "১০. আন্দামান ও নিকোবর দ্বীপপুঞ্জ ভারতের কোন হটস্পটের অন্তর্গত?",
            options: ["ইন্দো-বার্মা", "সুন্দাল্যান্ড (Sundaland)", "পূর্ব হিমালয়", "পশ্চিমঘাট"],
            answer: "সুন্দাল্যান্ড (Sundaland)",
            explanation: "আন্দামান ও নিকোবর দ্বীপপুঞ্জের উদ্ভিদ ও প্রাণীবৈচিত্র্য এই সুন্দাল্যান্ড হটস্পটের অংশ।"
        },
        {
            question: "১১. যে সব উদ্ভিদ বা প্রাণী পৃথিবীর একটি নির্দিষ্ট অঞ্চল ছাড়া অন্য কোথাও পাওয়া যায় না, তাদের কী বলে?",
            options: ["বহিরাগত প্রজাতি", "এনডেমিক প্রজাতি (Endemic species)", "বিলুপ্ত প্রজাতি", "সর্বজনীন প্রজাতি"],
            answer: "এনডেমিক প্রজাতি (Endemic species)",
            explanation: "হটস্পটগুলোর একটি বড় বৈশিষ্ট্য হলো সেখানে প্রচুর এনডেমিক বা নিজস্ব স্থানীয় প্রজাতি বাস করে।"
        },
        {
            question: "১২. ইন্দো-বার্মা হটস্পটে পাওয়া যায় এমন একটি প্রাণী হলো—",
            options: ["ডলফিন", "লায়ন-টেল্ড ম্যাকাক", "স্বাদু জলের কচ্ছপ এবং কুমির", "তুষার চিতা"],
            answer: "স্বাদু জলের কচ্ছপ এবং কুমির",
            explanation: "উত্তর-পূর্ব ভারতের রাজ্যগুলো এবং মায়ানমার-চীন সংলগ্ন এই হটস্পটে এরা পাওয়া যায়।"
        },
        {
            question: "১৩. সুন্দরবন অঞ্চলের উদ্ভিদ ও প্রাণীবৈচিত্র্য কোন হটস্পট এলাকার সাথে সামঞ্জস্যপূর্ণ?",
            options: ["পূর্ব হিমালয়", "সুন্দাল্যান্ড", "ইন্দো-বার্মা", "পশ্চিমঘাট"],
            answer: "সুন্দাল্যান্ড",
            explanation: "সুন্দরবনের ম্যানগ্রোভ অঞ্চল ভৌগোলিকভাবে সুন্দাল্যান্ড হটস্পটের অন্তর্ভুক্তির সাথে মেলে।"
        },
        {
            question: "১৪. বাস্তুতন্ত্রের ভারসাম্য রক্ষায় জীববৈচিত্র্যের ভূমিকা কী?",
            options: ["কোনো ভূমিকা নেই", "একটি প্রজাতি বিলুপ্ত হলে খাদ্যশৃঙ্খল ভেঙে পড়ে এবং বাস্তুতন্ত্র অকেজো হয়ে যায়", "এটি কেবল মাটির উর্বরতা বাড়ায়", "এটি দূষণ বাড়ায়"],
            answer: "একটি প্রজাতি বিলুপ্ত হলে খাদ্যশৃঙ্খল ভেঙে পড়ে এবং বাস্তুতন্ত্র অকেজো হয়ে যায়",
            explanation: "প্রতিটি জীব একে অপরের ওপর খাদ্যের জন্য নির্ভরশীল, তাই একটি জীব হারিয়ে গেলে পুরো সিস্টেম বিপর্যস্ত হয়।"
        },
        {
            question: "১৫. ভারতের মেগা-জীববৈচিত্র্য দেশের তালিকায় স্থান পাওয়ার প্রধান কারণ কী?",
            options: ["এখানে শুধু বাঘ পাওয়া যায় বলে", "৪৫ হাজার উদ্ভিদ এবং তার দ্বিগুণ প্রাণী প্রজাতির বিশাল বৈচিত্র্যের কারণে", "ভারতের জনসংখ্যা বেশি বলে", "এখানে বরফ বেশি বলে"],
            answer: "৪৫ হাজার উদ্ভিদ এবং তার দ্বিগুণ প্রাণী প্রজাতির বিশাল বৈচিত্র্যের কারণে",
            explanation: "এই বিশাল বৈচিত্র্যই ভারতকে পৃথিবীর ১৭টি মেগা বায়োডাইভার্সিটি দেশের একটিতে পরিণত করেছে।"
        }
    ];

    let currentQuestionIndex = 0;
    let score = 0;
    let selectedOption = "";
    let userAnswers = [];
    let timerInterval;

    const questionTextEl = document.getElementById("question-text");
    const optionsListEl = document.getElementById("options-list");
    const nextBtn = document.getElementById("next-btn");
    const qCounterEl = document.getElementById("q-counter");
    const timerDisplayEl = document.getElementById("timer-display");

    const resultSection = document.getElementById("result-section");
    const reviewContainer = document.getElementById("review-container");
    const finalScoreEl = document.getElementById("final-score");

    function startTimer(durationInSeconds) {
        let timeRemaining = durationInSeconds;
        
        timerInterval = setInterval(() => {
            let minutes = Math.floor(timeRemaining / 60);
            let seconds = timeRemaining % 60;

            minutes = minutes < 10 ? "0" + minutes : minutes;
            seconds = seconds < 10 ? "0" + seconds : seconds;

            timerDisplayEl.innerText = `${minutes}:${seconds}`;

            if (timeRemaining <= 0) {
                clearInterval(timerInterval);
                alert("আপনার কুইজের নির্ধারিত ১০ মিনিট সময় শেষ হয়ে গেছে! কুইজটি স্বয়ংক্রিয়ভাবে সাবমিট করা হচ্ছে।");
                showResults();
            }
            timeRemaining--;
        }, 1000);
    }

    function loadQuestion() {
        selectedOption = "";
        const currentData = quizData[currentQuestionIndex];

        qCounterEl.innerText = `প্রশ্ন: ${currentQuestionIndex + 1} / ${quizData.length}`;
        questionTextEl.innerText = currentData.question;
        optionsListEl.innerHTML = "";

        if(currentQuestionIndex === quizData.length - 1) {
            nextBtn.innerText = "কুইজ সম্পূর্ণ সাবমিট করুন";
            nextBtn.style.backgroundColor = "#27ae60";
        } else {
            nextBtn.innerText = "পরবর্তী প্রশ্ন";
            nextBtn.style.backgroundColor = "var(--primary-color)";
        }

        currentData.options.forEach(option => {
            const li = document.createElement("li");
            li.classList.add("option-item");
            li.innerText = option;
            li.onclick = () => selectOption(li, option);
            optionsListEl.appendChild(li);
        });
    }

    function selectOption(li, option) {
        const allOptions = document.querySelectorAll(".option-item");
        allOptions.forEach(opt => opt.classList.remove("selected"));
        li.classList.add("selected");
        selectedOption = option;
    }

    function saveStudentReport(finalScore) {
        let userReport = JSON.parse(localStorage.getItem(`quiz_report_ch5_s6_${currentUsername}`)) || { bestScore: 0, attempts: 0 };
        
        userReport.attempts += 1; 
        if (finalScore > userReport.bestScore) {
            userReport.bestScore = finalScore; 
        }

        localStorage.setItem(`quiz_report_ch5_s6_${currentUsername}`, JSON.stringify(userReport));
    }

    function showResults() {
        clearInterval(timerInterval);
        quizSection.style.display = "none";
        resultSection.style.display = "block";
        finalScoreEl.innerText = `স্কোর: ${score} / ${quizData.length}`;

        saveStudentReport(score);

        reviewContainer.innerHTML = ""; 
        quizData.forEach((item, index) => {
            const userAnswer = userAnswers[index];
            const isCorrect = userAnswer === item.answer;

            const reviewHtml = `
                <div class="review-item">
                    <div class="review-q">${item.question}</div>
                    <div class="review-ans">
                        আপনার উত্তর: <span class="${isCorrect ? 'ans-correct' : 'ans-wrong'}">
                            ${userAnswer ? userAnswer : 'উত্তর দেননি (Skipped/Time Out)'}
                        </span>
                    </div>
                    ${!isCorrect ? `<div class="review-ans">সঠিক উত্তর: <span class="ans-correct">${item.answer}</span></div>` : ''}
                    <div class="explanation">
                        <strong>ব্যাখ্যা:</strong> ${item.explanation}
                    </div>
                </div>
            `;
            reviewContainer.innerHTML += reviewHtml;
        });
    }

    nextBtn.addEventListener("click", () => {
        if (selectedOption === "") {
            const confirmSkip = confirm("আপনি কোনো অপশন সিলেক্ট করেননি। আপনি কি এই প্রশ্নটি স্কিপ (Skip) করতে চান?");
            if (!confirmSkip) {
                return; 
            }
            userAnswers[currentQuestionIndex] = null; 
        } else {
            userAnswers[currentQuestionIndex] = selectedOption;
            if (selectedOption === quizData[currentQuestionIndex].answer) {
                score++;
            }
        }

        currentQuestionIndex++;

        if (currentQuestionIndex < quizData.length) {
            loadQuestion();
        } else {
            showResults();
        }
    });
</script>

</body>
</html>
