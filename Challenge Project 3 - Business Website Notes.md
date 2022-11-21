# Challenge Project 3 - Business Website Notes 
<br><br><br>

## Problems Encountered
---
1. **Entering Flavicon Picture**<br>
   `SOLUTION => `Flavicon is added into `Head` section such as:
   ```    
   <link rel="icon" type="image/x-icon" href="/resources/pictures/favicon/favicon.ico">
   ```

2. **How to lower opacity of background image without affecting text?**
   `SOLUTION => `https://coder-coder.com/background-image-opacity/
      1. Put the background image into a pseudo-element of the parent.
      ```
      .hero {
    position: relative; 
    height: 100vh;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
   }

   .hero::before {    
      content: "";
      background-image: url('https://placekitten.com/1200/800');
      background-size: cover;
      position: absolute;
      top: 0px;
      right: 0px;
      bottom: 0px;
      left: 0px;
      opacity: 0.75;
   }

      h1 {
   position: relative;
   color: #ffffff;  
   font-size: 14rem;
   line-height: 0.9;
   text-align: center;
   }
   ```
   # !!! HUGE PROBLEM !!!

   `PROBLEM:` <br> 
   **Website(CSS) was not working properly when opening just from folder and not from VS Live server.**

   For example the background-image would not load, or downloaded font woul not work.

   `SOLUTION => `<BR>
   The problem was in the fact that CSS would not load relative or absolute path to the image(note that HTML was working fine and had no problem with absolute path).

   Problem was solved by changing slash sign from forward slash to backward slash in absolute way as can be seen below: <br><br>


   This **WOULD NOT** work and picture **WOULD NOT** be loaded:
   ```
   background-image: url('C:\Users\lukem\test\resources\images\banner.jpg')
   ```

   In order for CSS to load and access image, the path needed to be changed into this: => **!!! THIS IS WORKING !!!**
   ```
     background-image: url('C:/Users/lukem/test/resources/images/banner.jpg');
   ```

   Second solution that would be working is:
   ```
   background-image: url('C:\\Users\\lukem\\test\\resources\\images\\banner.jpg');
   ```

   Another way is of course use **Relative Path** but, I MUST make **EXTRA CARE** that I am indeed using the correct syntax. If for example the picture is in another folder, I must always use *2 dots*:
   ```
   url('../images/photo.jpg')
   ```
   <br><br>
   3.**How to use TODO and IMPORTNAT in comments:**

      a) Using TODO:
               
            <!-- TODO: This is the syntax for TODO-->

      b) Using IMPORTANT:
            
            <!-- !! This note is important!!>

<br>

## **PROBLEM** 
---
### **How to move jumping anchors(local navigation within page) to EXACT location?**

<br><br>
## **SOLUTION**
---
https://stackoverflow.com/questions/4086107/fixed-page-header-overlaps-in-page-anchors



My solution combines the target and before selectors for our CMS. Other techniques don't account for text in the anchor. Adjust the height and the negative margin to the offset you need...
```
:target::before {
    content: '';
    display: block;
    height:      180px;
    margin-top: -180px;
}
```

## **PROBLEM**
---
### **How to clear floats after div?** <br><br>

## **SOLUTION**
---
Use **ClearFix Hack**:
```
.div_section::after {
    content: "";
    clear: both;
    display: table;
  }
  ```