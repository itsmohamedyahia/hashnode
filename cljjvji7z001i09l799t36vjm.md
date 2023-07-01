---
title: "The Step Of Design In The Software Process"
datePublished: Sat Jul 01 2023 10:42:25 GMT+0000 (Coordinated Universal Time)
cuid: cljjvji7z001i09l799t36vjm
slug: the-step-of-design-in-the-software-process
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1688208077790/560c84d2-9754-47f3-a490-b0bd81027e4a.png
tags: tutorial, software-development, beginners, software-engineering, object-oriented-programming

---

### WHY DO WE NEED A DESIGN STEP?

to avoid complications (that's a typical medical term right there, ok). **WHAT ARE THE COMPLICATIONS?**

Project Failure or delay and that happens most of the time if the project doesnt satify the client requirements. Why wouldnt it satify the requirements? Didnt we build it according to the requirements??! That's the point, we didnt. We didnt take the requirements properly.

And that's the first step in software design. Eliciting Requirements.

### STEPS OF THE DESIGN PROCESS

1. Eliciting Requirements

   - other than what the client might tell you, you have to ask follow-up questions to get all the details you need (the depth and width of the details depends on what methodology are you following: the waterfall method or the agile metho)
   - if there is something that might seem contradictory or not logical about the requirements, you have to ask for clarification

2. Conceptual design

   - in this step, you make conceptual mockups that show HOW the requirements will be met. You should avoid any technical details in this step.

   - ![image](https://i1.pickpik.com/photos/114/603/746/paper-sketch-ux-web-design-preview.jpg)

   <small>Web Design Wireframes on Paper. [PickPik](https://www.pickpik.com/web-design-wireframes-paper-sketch-ux-art-and-design-81471)</small>

   - you should think about the major components of your project and maybe divide a big component in other smaller but still big components.

   - you should think about the connections of the components to one another and the responbilities of each component.

3. Technical Design

   - in this step, you will build a technical diagram that show the implementation details that will lead to satifying the requirements.

   - you should furthur divide the components into atomic components in which each has a one responsibility

   > for example, you are building a house, you began by doing a conceptual mockup of the internals of the house, where you drew the major components or rooms and the connections (doors) between each component and the other

![image](https://images.rawpixel.com/image_1000/cHJpdmF0ZS9sci9pbWFnZXMvd2Vic2l0ZS8yMDIzLTAzL2ZsNTAwMTI2MzkxNzMtaW1hZ2UuanBn.jpg)

<small>Multiple Housing Drawing 1940s Oak Ridge. CC0 1.0. [U.S. Department of Energy](https://www.rawpixel.com/image/8734630/multiple-housing-drawing-1940s-oak-ridge).</small>

> Maybe, you need a studyroom and that room responsibility is to provide you with space and light (to help you study). Since its responsibility is to provide space, you have to think about the dimensions of that room and what dimensions will satisfy your requirements. Since its other responsibility is to provide light then you would need a light source, so for financial requirements, you decided to go for the sun as a light source during the day and a lamp during the night. How would the sunlight enter the room?? Yes, you will have to make a window. Thats a minor component. How much light do you need? you will have to think about the dimensions of the window, the luminosity of the lamp and so on and those are the technical details that will in the end satify the requirements.

When you are thinking about the technical details, issues might arise, like maybe one of your requirements is a big living room not less than 4 x 5 meters and also another requirement is a big studyroom not less than 4 x 5 meters. For simplicity, lets say that the house only consists of those two rooms and you only have 8 x 8 meters to work with. Then satisfying both requirements is unfeasible. You will have to communicate that with the client and reach a compromise and edit your conceptual design.

Your conceptual design doesnt have to be perfect but at least take your time into developing an acceptable design where you can refine later while thinking about the components connections or the technical details.

### HOW TO WRITE DOWN OR EXPRESS REQUIREMENTS

One way is through `user stories`. If you have a requirement of a search bar, you express it through this format:

> As a (customer), I would like to (search for products) so I can (can buy them) .

The user is identified because there can be different kinds of users or even an admin using another route of the website to make changes like add blog posts or sth.

The reason is identified because it is important to know the why of the action, we dont want to build a feature that turns out to be useless.

### USERS AND COMPONENTS CORRESPOND TO OBJECTS

When we are listing out the components of the software during the conceptual mockups and the technical diagrams, each component will correspond to an object in code. For example, the studyroom will be an object. That object will have a window as a property. It will have a width and a length. The room might be dark or light depending on the window status, if it is closed or open, so it will have an brightness property too. The window is another object, it is an object inside (a property of) the studyroom. That window will have another properties too, it will have methods or functions for opening and closing it.

Users also correspond to objects. A user will have properties that might include their personal information.
