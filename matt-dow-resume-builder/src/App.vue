
<template>
  <main class="container">
    <div id="resume" class="d-flex">
      <div class="left-col">
        <div class="resume-section">
          <img v-bind:src="imageUrl" class="profile-pic" alt="profile picture">
          <div class="section-headline">
            {{ headlines[0] }}
          </div>
          <div>
            {{ introText }}
          </div>
        </div>
        <div class="resume-section">
          <div class="section-headline">
            {{ headlines[1] }}
          </div>
          <ul>
            <li>{{ contactInfo.phone }}</li>
            <li>{{ contactInfo.email }}</li>
            <li>{{ contactInfo.address }}</li>
          </ul>
        </div>
        <div class="resume-section">
          <div class="section-headline">
            {{ headlines[2] }}
          </div>
          <ul>
            <li v-for="(skill, index) in skills" :key="index">{{ skill }}</li>
          </ul>
        </div>
        <div class="resume-section">
          <div class="section-headline">
            {{ headlines[3] }}
          </div>
          <ul>
            <li>Data Analytics (General Assembly Online)</li>
            <li>Full-Stack Software Engineering (Prime Digital Academy)</li>
          </ul>
        </div>        
      </div>
      <div class="right-col">
        <h4 class="personal-name">
          {{ name }}
        </h4>
        <h4 class="personal-title">
          {{ title }}
        </h4>
        <h4 class="section-headline">
          Experience
        </h4>
        <div v-for="(item, index) in experience" :key="index" class="inner-section">
          <div>{{ item.title }}</div>
          <div class="d-flex justify-content-between">
            <div>{{ item.company }}, {{ item.location }}</div>
            <div>{{ item.date }}</div>
          </div>
          <ul>
            <li v-for="(desc, innerIndex) in item.description" :key="innerIndex">{{ desc }}</li>
          </ul>
        </div>
        
        <h4 class="section-headline">
          Education
        </h4>
        <div>{{ education.title }}</div>
        <div class="d-flex justify-content-between">
          <div>{{ education.university }}</div>
          <div>{{ education.date }}</div>
        </div>  
      </div>
    </div>
  </main>
</template>

<script>
export default {
  data() {
    return {
      name: "Matt Dow",
      title: "Software Developer | Technical Support Engineer",
      introText: "Software development professional with expertise in mobile and web applications, blending technical acumen with strong problem-solving and collaboration skills. Proven ability to deliver impactful solutions by leveraging experience in both tech and customer-facing roles from a previous career in commercial property management.",
      imageUrl: "/matt_dow_headshot.jpg",
      headlines: ["About me", "Contact", "Skills", "Certifications", "Experience", "Education"],
      contactInfo: {
        phone: "651-587-8454",
        email: "matt.dow.vo@gmail.com",
        address: "514 Portland Avenue, Saint Paul, MN 55102"
      },
      skills: ["JavaScript", "React", "React Native", "Vue", "Node.js", "Google Cloud Platform", "SQL"],
      experience: [
        {
          title: "Software Developer",
          company: "BetterYou",
          location: "Saint Paul, MN",
          date: "03/2022 - 07/2024",
          description: [
            "Rebuilt the app's sleep system in 2024, employing a new machine learning model and a new user-friendly interface to help users establish consistent bedtime routines.",
            "During the company's 2022 app and database overhaul, completely updated critical systems to modern development standards.",
            "Designed and implemented seamless system integrations for aggregating health and wellness data from a variety of sources, including Apple Health, Google Fit, and wearable devices.",
            "Led the Android app through a critical and time-sensitive Google Trust and Safety security assessment in May 2023, including the successful completion of a CASA security scan and subsequent thorough app review.",
            "Key Technologies Utilized: React Native, React Query, JavaScript, Node.js, Google Cloud Platform, Firebase, Swift, Java, Jest, and JUnit.",
          ]
        },
        {
          title: "Full Stack Software Engineering Student",
          company: "Prime Digital Academy",
          location: "Minneapolis, MN",
          date: "08/2021 - 01/2022",
          description: [
            "Coordinated and collaborated with developers, project managers, and UX designers for the client to build a proof-of-concept software marketplace prototype in a two-week sprint.",
            "Following Prime graduation, assisted the client's engineering team to convert the codebase to TypeScript.",
            "As a solo capstone project, created a disc golf score and note tracker.",
            "Technologies used: JavaScript, TypeScript, Node.js, Express, React.js, Redux, Saga, Chart.js, PostgreSQL, and Material-UI.",
          ]
        },
        {
          title: "Real Estate Manager",
          company: "Ryan Companies",
          location: "Minneapolis, MN",
          date: "2011 - 2020",
          description: [
            "Managed a 650,000 square foot class-A office building with two colleagues.",
            "Created a plan to sustain Ryan's culture as part of Ryan's 2015-16 Emerging Leaders Group.",
            "Raised over $300,000 during dozens of events as co-ambassador of Ryan's 2016 United Way Week.",
            "Facilitated a full lease turnover and four major tenant improvement projects over two years as lead manager for a downtown office building.",
            "Improved janitorial service, security, window cleaning, and elevator maintenance by crafting and enforcing contract language and regularly meeting with vendors.",
          ]
        }
      ],
      education: 
        {
          title: "Courses taken toward a Chemical Engineering Degree",
          university: "University of Wisconsin-Madison",
          date: "1997 - 2001",
        },
      
    }
  }
}
</script>

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

