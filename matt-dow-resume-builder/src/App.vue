
<template>
  <main class="container">
    <div id="resume" class="d-flex">
      <div class="left-col">
        <div class="resume-section">
          <div class="section-headline">
            About Me
          </div>
          <div>
            Software development professional with expertise in mobile and web applications, blending technical acumen with strong problem-solving and collaboration skills. Proven ability to deliver impactful solutions by leveraging experience in both tech and customer-facing roles from a previous career in commercial property management.
          </div>
        </div>
        <div class="resume-section">
          <div class="section-headline">
            Contact
          </div>
          <ul>
            <li>651-587-8454</li>
            <li>matt.dow.vo@gmail.com</li>
            <li>514 Portland Avenue, Saint Paul, MN, 55102</li>
          </ul>
        </div>
        <div class="resume-section">
          <div class="section-headline">
            Skills
          </div>
          <ul>
            <li>JavaScript</li>
            <li>React</li>
            <li>React Native</li>
            <li>Vue</li>
            <li>Node.js</li>
            <li>Google Cloud Platform</li>
            <li>SQL</li>
          </ul>
        </div>
        <div class="resume-section">
          <div class="section-headline">
            Certifications
          </div>
          <ul>
            <li>Data Analytics (General Assembly Online)</li>
            <li>Full-Stack Software Engineering (Prime Digital Academy)</li>
          </ul>
        </div>        
      </div>
      <div class="right-col">
        <h4 class="personal-name">
          Matt Dow
        </h4>
        <h4 class="personal-title">
          Software Developer | Technical Support Engineer
        </h4>
        <h4 class="section-headline">
          Experience
        </h4>
        <div>Software Developer</div>
        <div>BetterYou, Saint Paul, MN, 03/2022 - 07/2024</div>
        <ul>
          <li>
            Rebuilt the app's sleep system in 2024, employing a new machine learning model and a new user-friendly interface to help users establish consistent bedtime routines.
          </li>
          <li>
            During the company's 2022 app and database overhaul, completely updated critical systems to modern development standards.
          </li>
          <li>
            Designed and implemented seamless system integrations for aggregating health and wellness data from a variety of sources, including Apple Health, Google Fit, and wearable devices.
          </li>
           <li>
            Led the Android app through a critical and time-sensitive Google Trust and Safety security assessment in May 2023, including the successful completion of a CASA security scan and subsequent thorough app review.
          </li>
          <li>
            Key Technologies Utilized: React Native, React Query, JavaScript, Node.js, Google Cloud Platform, Firebase, Swift, Java, Jest, and JUnit.
          </li>
        </ul>
        <div>Full Stack Software Engineering Student</div>
        <div>Prime Digital Academy, Minneapolis, MN, 08/2021-01/2022</div>
        <ul>
          <li>
            Coordinated and collaborated with developers, project managers, and UX designers for the client to build a proof-of-concept software marketplace prototype in a two-week sprint.
          </li>
          <li>
            Following Prime graduation, assisted the client's engineering team to convert the codebase to TypeScript.
          </li>
          <li>
            As a solo capstone project, created a disc golf score and note tracker.
          </li>
          <li>
            Technologies used: JavaScript, TypeScript, Node.js, Express, React.js, Redux, Saga, Chart.js, PostgreSQL, and Material-UI.
          </li>
        </ul>
        <div>Real Estate Manager</div>
        <div>Ryan Companies, Minneapolis, MN, 09/2011-05/2020</div>
        <ul>
          <li>
            Managed a 650,000 square foot class-A office building with two colleagues.
          </li>
          <li>
            Created a plan to sustain Ryan's culture as part of Ryan's 2015-16 Emerging Leaders Group.
          </li>
          <li>
            Raised over $300,000 during dozens of events as co-ambassador of Ryan's 2016 United Way Week.
          </li>
          <li>
            Facilitated a full lease turnover and four major tenant improvement projects over two years as lead manager for a downtown office building.
          </li>
          <li>
            Improved janitorial service, security, window cleaning, and elevator maintenance by crafting and enforcing contract language and regularly meeting with vendors.
          </li>      
        </ul>
        <h4 class="section-headline">
          Education
        </h4>
        <div>Courses taken toward a Chemical Engineering Degree</div>
        <div>University of Wisconsin-Madison, 1997-2001</div>        
      </div>
    </div>
  </main>
</template>

<style scoped>
  #resume {
    box-shadow: rgba(50, 50, 93, 0.25) 0px 13px 27px -5px, rgba(0, 0, 0, 0.3) 0px 8px 16px -8px;
  /* DIN A4 standard paper size. commonly used for resumes
  For North America letter size use width: 8.5in; height: 11in; */
  height: 297mm;
  width: 210mm;
  }

  .left-col {
    width: 30%;
  }

  .right-col {
    width: 70%;
  }
</style>

