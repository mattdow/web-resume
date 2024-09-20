
<template>
  <main class="container">
    <div id="resume" class="d-flex">
      <div class="left-col">
        <ResumeSection>
          <img :src="imageUrl" class="profile-pic" alt="profile picture">
          <SectionHeadline 
            :headline="headlines[0]" 
            @headline-edited="updateHeadline($event, 0)"
          />         
          <div
            contenteditable="true"
            @input="updateProperty($event, 'introText')"          
          >
            {{ introText }}
          </div>
        </ResumeSection>
        <ResumeSection>
          <SectionHeadline 
            :headline="headlines[1]" 
            @headline-edited="updateHeadline($event, 1)"
          />
          <Contact
            :contactInfo="contactInfo"
            @edit="updateNestedProperty"
          />          
        </ResumeSection>
        <ResumeSection>
          <SectionHeadline 
            :headline="headlines[2]" 
            @headline-edited="updateHeadline($event, 2)"
          />    
          <ul>
            <li 
              v-for="(skill, index) in skills" 
              :key="index"
              contenteditable="true"
              @input="updateNestedProperty($event, 'skills', index)"
            >
              {{ skill }}
            </li>
          </ul>
          <EditButtons 
            @add-click="skills.push('new entry')" 
            @remove-click="skills.pop()"
            :show-remove-btn="skills.length > 0"
          />
        </ResumeSection>
        <ResumeSection>
          <SectionHeadline 
            :headline="headlines[3]" 
            @headline-edited="updateHeadline($event, 3)"
          />    
          <ul>
            <li
              v-for="(certification, index) in certifications"
              :key="index"
              contenteditable="true"
              @input="updateNestedProperty($event, 'certifications', index)"
            > 
              {{ certification }}
            </li>
          </ul>
          <EditButtons 
            @add-click="certifications.push('new entry')" 
            @remove-click="certifications.pop()"
            :show-remove-btn="certifications.length > 0"
          />
        </ResumeSection>       
      </div>
      <div class="right-col">
        <div
          class="personal-name"
          contenteditable="true"
          @input="updateProperty($event, 'name')"
        >
          {{ name }}
        </div>

        <div
          class="personal-title"
          contenteditable="true"
          @input="updateProperty($event, 'title')"
        >
          {{ title }}
        </div>
        <div class="d-flex justify-content-between">
          <SectionHeadline 
              :headline="headlines[4]" 
              @headline-edited="updateHeadline($event, 4)"
          />    
          <EditButtons :show-remove-btn="false" @add-click="addExperience" text-add="Add Experience"/>
        </div>
        <div 
          v-for="(item, index) in experience" 
          :key="index" 
          class="inner-section">
          <div class="d-flex justify-content-between">
            <div
            contenteditable="true"
            @input="updateExperience($event, 'title', index)"
            >
            {{ item.title }}
            </div>
            <EditButtons @remove-click="removeExperience(index)" :show-add-btn="false" text-remove="Remove"/>
          </div>
          
          <div class="d-flex justify-content-between">
            <div>
              <span contenteditable="true" 
                @input="updateExperience($event, 'company', index)"
              >
                {{ item.company }}
              </span>,
              <span 
                contenteditable="true" 
                @input="updateExperience($event, 'location', index)"
              >
                {{ item.location }}
              </span>
            </div>
            <div
              contenteditable="true"
              @input="updateExperience($event, 'date', index)"
            >
              {{ item.date }}
            </div>
          </div>
          <ul>
            <li 
            v-for="(desc, innerIndex) in item.description" 
            :key="innerIndex"
            contenteditable="true"
            @input="updateExperienceDescription($event, index, innerIndex)">
            {{ desc }}
          </li>
          </ul>
          <EditButtons
            @add-click="item.description.push('new entry')"
            @remove-click="item.description.pop()"
            :show-remove-btn="item.description.length > 0"
          />
        </div>
        <div class="d-flex">
          <SectionHeadline 
            :headline="headlines[5]" 
            @headline-edited="updateHeadline($event, 5)"
          />
          <EditButtons :show-remove-btn="false" @add-click="addEducation"/>   
        </div>
         
          <div
            v-for="(item, index) in education"
            :key="index"
            class="inner-section">
            <div class="d-flex justify-content-between">
              <div
                contenteditable="true"
                @input="updateEducation($event, 'title', index)"
              >
                {{ item.title }}
              </div>
              <EditButtons :show-add-btn="false" @remove-click="removeEducation" />
            </div>
            

            <div class="d-flex justify-content-between">
              <div>
                <span
                  contenteditable="true"
                  @input="updateEducation($event, 'university', index)">
                  {{ item.university }}
                </span>,
                <span
                  contenteditable="true"
                  @input="updateEducation($event, 'location', index)">
                  {{ item.location }}
                </span>
              </div>

              <div
                contenteditable="true"
                @input="updateEducation($event, 'date', index)">
                {{ item.date }}
              </div>
            </div>
            <ul>
              <li
                v-for="(desc, innerIndex) in item.description"
                :key="innerIndex"
                contenteditable="true"
                @input="updateEducationDescription($event, index, innerIndex)">
                {{ desc }}
              </li>
            </ul>

          </div>
      </div>
    </div>
  </main>
</template>

<script>
import ResumeSection from './components/ResumeSection.vue';
import SectionHeadline from './components/SectionHeadline.vue';
import Contact from './components/Contact.vue';
import EditButtons from './components/EditButtons.vue';
export default {
  components: {
    ResumeSection,
    SectionHeadline,
    Contact,
    EditButtons,
  },
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
        address: "514 Portland Avenue Saint Paul, MN 55102"
      },
      skills: ["JavaScript", "React", "React Native", "Vue", "Node.js", "Google Cloud Platform", "SQL"],
      certifications: ["Data Analytics (General Assembly Online)", "Full-Stack Software Engineering (Prime Digital Academy)"],
      experience: [
        {
          title: "Software Developer",
          company: "BetterYou",
          location: "Saint Paul, MN",
          date: "03/2022 - 07/2024",
          description: [
            "Rebuilt the app's sleep system in 2024, employing a new machine learning model and a new user-friendly interface to help users establish consistent bedtime routines.",
            "During the company's 2022 app and database overhaul, completely updated critical systems to modern development standards.",
            "Designed and implemented seamless API integrations for aggregating health and wellness data from a variety of sources, including Apple Health, Google Fit, and wearable devices.",
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
            "Technologies used: JavaScript, TypeScript, Node.js, Express, React.js, Redux, Saga, Chart.js, PostgreSQL, and Material-UI.",
          ]
        },
        {
          title: "Real Estate Manager",
          company: "Ryan Companies",
          location: "Minneapolis, MN",
          date: "09/2011 - 05/2020",
          description: [
            "Managed a 650,000 square foot class-A office building with two colleagues.",
            "Created a plan to sustain Ryan's culture as part of Ryan's 2015-16 Emerging Leaders Group.",
            "Raised over $300,000 during dozens of events as co-ambassador of Ryan's 2016 United Way Week.",
            "Facilitated a full lease turnover and four major tenant improvement projects over two years as lead manager for a downtown office building.",
          ]
        }
      ],
      education: [
        {
          title: "Courses taken toward a Chemical Engineering Degree",
          university: "University of Wisconsin-Madison",
          date: "1997 - 2001",
          description: [],
        },
      ],
      
    }
  },
  methods: {
    updateHeadline(newValue, index) {
      this.headlines[index] = newValue
    },
    updateProperty(event, key) {
      this[key] = event.target.innerText;
    },
    updateNestedProperty(event, key1, key2) {
      this[key1][key2] = event.target.innerText;
    },
    updateExperience(event, key, index) {
      this.experience[index][key] = event.target.innerText;
    }, 
    updateExperienceDescription(event, index1, index2) {
      this.experience[index1]['description'][index2] = event.target.innerText;
    },
    updateEducation(event, key, index) {
      this.education[index][key] = event.target.innerText;
    },
    updateEducationDescription(event, index1, index2) {
      this.education[index1]["description"][index2] = event.target.innerText;
    },
    addExperience() {
      this.experience.unshift({
        title: "Job Title",
        company: "Company",
        location: "Location",
        date: "MM/YYYY - MM/YYYY",
        description: [
          "description"
        ]
      });
    },
    addEducation() {
      this.education.unshift({
        title: "Education Title",
        university: "Institution",
        location: "Location",
        date: "date range",
        description: [
          "description"
        ]
      });
    },
    removeExperience(index) {
      this.experience.splice(index, 1); 
    },
    removeEducation(index) {
      this.education.splice(index, 1);
    },
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

