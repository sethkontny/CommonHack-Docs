CommonHack.json
===============

## How does CommonHack Work?

### Hackers

For Hackers, you'll be able to log in to [Commonhack](http://commonhack.org) with your Github profile.

From there, fill out your profile, and select which sections you would like to be public or hackathon-only.

Navigate to the hackathon section, where you can select which hackathons you permit to see your data.

*Those who have signed up for HackMIT 2014 may have some of their data pre-populated!*

### Organizers

Organizers will sign in and create their account using a Twitter account. They will then need
to be manually verified, by contacting [contact@commonhack.org](mailto:contact@commonhack.org).

Once an account is verified, you will be able to create a hackathon.

Creating a hackathon generates an API key for that hackathon, which will allow you to query for data.

#### API Docs

##### GET http://commonhack.org/api/hackers

For a valid API Key, the GET will return all hackers who have selected your hackathon to be visible.

```javascript
// Server will return:

{
  username: String,
  lastUpdated: Date,

  bio: {
    firstName: String,
    lastName: String,
    picture: String,        // Link to picture
    summary: String
  },

  personal {
    gender: String,
    dietaryRestrictions: [
      String
    ]
  },

  contact: {
    email: String,  
    phone: String,          // Formatted as +### (###) ### ####, ex. +1 123 555 1234
    resume: String          // Link to resume
  },

  websites: {
    personal: String,       // Link to website 
    blog: String            // Link to blog
  },

  profiles: {
    facebook: String,       // Link to facebook profile
    twitter: String,        // Twitter handle/username
    linkedin: String,       // Link to linked in profile
    github: String,         // Github username
    dribbble: String,       // Dribbble username
    behance: String         // Behance username
  },

  location: {
    city: String,
    countryCode: String,    // Ex. "US"
    region: String          // If not state
    state: String           // Ex. "MA"
  },

  education: [
    {
      institution: String,  // Name, ex. "MIT"
      areas: [
        String              // Ex. "Computer Science"
      ],
      studyType: String,    // Ex. "Bachelor's"
      classYear: Number     // Ex. 2016
    } 
  ],

  work: [
    {
      company: String,      // Name, ex. "Groupon"
      position: String,     // Ex. "Software Engineering Intern"
      start: Date,
      end: Date,
      description: String
    }
  ],

  hackathons: [
    {
      name: String,
      season: String,       // Ex. "Summer"
      year: Number,         // Ex. 2014
      awards: [
        {
          title: String,
          description: String
        }
      ],
      project: {
        title: String,
        description: String,
        link: String,
        image: String,      // Link to image
        technologies: [
          String            // Ex. "Firebase"
        ],
        teammates: [
          String            // Github/CommonHack usernames
        ]
      }
    } 
  ],

  projects: [
    {
      title: String,
      description: String,
      link: String,
      image: String,        // Link to image
      technologies: [
        String              // Ex. "Firebase"
      ],
      teammates: [
        String              // Github/CommonHack usernames
      ]
    }
  ],

  skills: [
    String                  // Ex. "Javascript" 
  ]
}


```
