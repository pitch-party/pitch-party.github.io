# Pitch Party 
* Language used: html, css, js
* Toolkit : boostrap (version: 5.0.2)
* Developed by [ETC Sci-com Center](https://projects.etc.cmu.edu/scicom-center/)
* Technical contact information: 
    * Phoebe Wang: hsuanjuw@andrew.cmu.edu / hsuanju.wang@gmail.com 

## Page description

* **index.html**: The page with the Start button and Rules button
* **gamePage.html**: The page for choosing Funder and Designer roles for the first round
* **gamePage2.html**: The page for choosing Funder and Designer roles after the first round
* **investorPage.html**: All Funder pages
* **designerPage.html**: All Designer pages
* **winPage.html**: The Designer's Pitch Accepted page 

## CSS description
**style.css**: All the style are in this file.

## JS description
* **gamePage.js**: Scripts used in investorPage.html, designerPage.html
* **contentGenerate.js**: Scripts about generating topics, requirement and wild cards.
* **scoring.js**: Scripts about counting the rounds that a player has played and pitches being accepted.

## How to add pitch topics
* General information: 
    * Currently there are 16 topics 
    * They are stored in the dictionary "contentDic" in **contentGenerate.js**
    * Each topic includes: 
        * topic (**must**)
        * category (**must**) : Technology /Science /Diversity (Three type)
        * inspiration (optional. If you want to add inspiration, there should be **4** inspirations)
        * imgs: (optional. If you want to add inspiration imgs, there should be **4** inspiration imgs)
    * All inspiration imgs should be stored in: **img/inspiration** file
 
    Example for the first topic:
    ```
    0:{
        topic : "Use AR (Augmented Reality) for an educational experience",
        category : "Technology",
        inspiration : [
            "Augmented reality (AR) is an interactive experience of a real-world environment where the objects that reside in the real world are enhanced by computer-generated perceptual information.",
            "Mobile phone manufacturers like Apple are combining hardware with machine learning and cutting‑edge developer tools to enable realistic and engaging AR experiences.",
            "Projected AR is technology that directly overlays digitals projections onto the physical world. Unlike smartphone or wearable AR, projected AR does not typically require a device to mediate and project imagery.",
            "Hololens is a pair of mixed reality smart glasses developed and manufactured by Microsoft."
          ],
        imgs : [
            "img/inspiration/AR_AR.png",
            "img/inspiration/AR_Mobile_AR.png",
            "img/inspiration/AR_Projected_AR.png",
            "img/inspiration/AR_Hololens.png"
          ]
    }
    ```
* Step by step:
    * Step 1(Skip this step if you don't want to add inspiration): Add inspiration image to **img/inspiration** file 
    * Step 2: Open contentGenerate.js
    * Step 3: Find contentDic = {...} (In the first row)
    ```
    let contentDic = {
      0:{
          topic : "Use AR (Augmented Reality) for an educational experience",
          category : "Technology",
          ...
      },
      ...
  }
    ```
    * Step 4: Scroll down to 17 (It's 17 because we skip two numbers due to not using "I" and "O" for topic codes)
    ```
  17:{
          topic : "Create a VR (Virtual Reality) experience on the pandemic",
          category : "Technology",
          inspiration : [
            "Virtual reality (VR) is the experience where users feel immersed in a simulated world, via hardware (headsets) and software.",
            "Oculus (Meta) Quest 2 is one of the best selling VR Headsets. It aims to create virtual social spaces. ",
            "The Virtuix Omni is an omnidirectional treadmill simulator for virtual reality games and other applications. It uses a platform to simulate locomotion i.e. the motion of walking.",
            "VR Gloves provide hand tracking and haptic feedback to give users a more immersive experience."      
          ],
          imgs : [
            "img/inspiration/VR_VRHeadset.png",
            "img/inspiration/VR_Quest2.png",
            "img/inspiration/VR_TheVirtuixOmni.png",
            "img/inspiration/VR_VRGloves.png"
          ]
    }
    ```
    * Step 5: Add a comma after the } 
    ```
  17:{
          topic : "Create a VR (Virtual Reality) experience on the pandemic",
          category : "Technology",
          inspiration : [
            "Virtual reality (VR) is the experience where users feel immersed in a simulated world, via hardware (headsets) and software.",
            "Oculus (Meta) Quest 2 is one of the best selling VR Headsets. It aims to create virtual social spaces. ",
            "The Virtuix Omni is an omnidirectional treadmill simulator for virtual reality games and other applications. It uses a platform to simulate locomotion i.e. the motion of walking.",
            "VR Gloves provide hand tracking and haptic feedback to give users a more immersive experience."      
          ],
          imgs : [
            "img/inspiration/VR_VRHeadset.png",
            "img/inspiration/VR_Quest2.png",
            "img/inspiration/VR_TheVirtuixOmni.png",
            "img/inspiration/VR_VRGloves.png"
          ]
    },
    ```
    * Step 6: Add the next topic (starts with 18) in the following format
    Example of adding topic **with** inspirations:
    ```
    18:{
        topic : "xxx",
        category : "xxx"
        inspiration : [
            "xxx",
            "xxx",
            "xxx",
            "xxx"
          ],
        imgs : [
            "img/inspiration/imageName"",
            "img/inspiration/imageName"",
            "img/inspiration/imageName"",
            "img/inspiration/imageName""
          ]         
    },
    ```
    Example of adding topic **without** inspirations:
    ```
    18:{
        topic : "xxx",
        category : "xxx"        
    },
    ```
    
    ** **Make sure to add the comma at the end and not to add the comma for the last one**
    
    
## How to add Requirement
* General information: 
    * They are stored in the array "refinements " in **contentGenerate.js**
* Step by step:
    * Step 1: Open contentGenerate.js
    * Step 2: Find refinements =[...]
    ```
    const refinements = [
      "Understandable for non-English speakers",
      "Includes all age groups", 
      "Accessible for physically disabled individuals",
      "Easy to maintain social distance",
      "Acts as a local landmark",
      "Can be a traveling exhibit",
      "Requires communication with other visitors",
      "Integrates storytelling into the experience",
      "Lets visitors become a permanent part of the experience",
      "Lets visitors enjoy a personalized experience", 
      "Improves visitors’ mental health",
      "Costs more than $100 to visit",
      "Requires visitors to wear sports clothes",
      "Open only at night",
      "Open for only 1 hour a day",
      "Located on top of a mountain",
      "Located at a public transit stop",
      "Involves pop culture such as anime or superheroes",
      "Requires visitors to wear costumes", 
      "Primarily targeted towards visitors’ pets", 
      "Incorporates edible materials",
      "Suitable for a romantic date night",
      "Can be easily updated yearly",
      "Only lasts for 24 hours"
    ];    
    ```
     * Step 3: Add a comma in the last row and add new requirements below
    ```
    const refinements = [
      "Understandable for non-English speakers",
      "Includes all age groups", 
      "Accessible for physically disabled individuals",
      "Easy to maintain social distance",
      "Acts as a local landmark",
      "Can be a traveling exhibit",
      "Requires communication with other visitors",
      "Integrates storytelling into the experience",
      "Lets visitors become a permanent part of the experience",
      "Lets visitors enjoy a personalized experience", 
      "Improves visitors’ mental health",
      "Costs more than $100 to visit",
      "Requires visitors to wear sports clothes",
      "Open only at night",
      "Open for only 1 hour a day",
      "Located on top of a mountain",
      "Located at a public transit stop",
      "Involves pop culture such as anime or superheroes",
      "Requires visitors to wear costumes", 
      "Primarily targeted towards visitors’ pets", 
      "Incorporates edible materials",
      "Suitable for a romantic date night",
      "Can be easily updated yearly",
      "Only lasts for 24 hours",
      "New Requirement 1",
      "New Requirement 2"
    ];    
    ```
    ** **Make sure not to add the comma for the last one**

## How to add Wild Cards
* General information: 
    * They are stored in the array "personalInterests " in **contentGenerate.js**
* Step by step:
    * Step 1: Open contentGenerate.js
    * Step 2: Find personalInterests =[...]
    ```
    const personalInterests=[
      "Makes you laugh out loud",
      "Your parent would enjoy (or would have enjoyed) the experience",
      "Uses technology that you’re personally unfamiliar with",
      "Uses technology that your organization already owns", 
      "Similar to an existing experience you know about",
      "You’re an animal-lover",
      "You’re a nature-lover",
      "You want the pitch with the shortest explanation", 
      "You want the most expensive pitch",
      "You want the most affordable pitch",
      "Lends itself to being featured on social media",
      "Easiest pitch for you to visualize in your mind", 
      "You want high visitor throughput",
      "Uses the least space",
      "Young children would enjoy the experience",
      "Easy to reproduce and sell to other science museums",
      "An exhibit that your boss would love"
    ];   
    ```
     * Step 3: Add a comma in the last row and add new requirements below
    ```
    const personalInterests=[
      "Makes you laugh out loud",
      "Your parent would enjoy (or would have enjoyed) the experience",
      "Uses technology that you’re personally unfamiliar with",
      "Uses technology that your organization already owns", 
      "Similar to an existing experience you know about",
      "You’re an animal-lover",
      "You’re a nature-lover",
      "You want the pitch with the shortest explanation", 
      "You want the most expensive pitch",
      "You want the most affordable pitch",
      "Lends itself to being featured on social media",
      "Easiest pitch for you to visualize in your mind", 
      "You want high visitor throughput",
      "Uses the least space",
      "Young children would enjoy the experience",
      "Easy to reproduce and sell to other science museums",
      "An exhibit that your boss would love",
      "New wild card 1",
      "New wild card 2"
    ];   
    ```
    ** **Make sure not to add the comma for the last one**






