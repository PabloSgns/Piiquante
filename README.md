<!-- PROJECT LOGO -->
<br />
<div align="center">
  <a href="https://github.com/PabloSgns/Piiquante">
    <img src="https://github.com/PabloSgns/Piiquante/blob/main/readme_img/logo.png" alt="Logo" width="600" height=300">
  </a>

<h3 align="center">Kanap</h3>

  <p align="center">
    This project is the n°6 of OpenClassrooms Web Developper course which consists in building a secure API for a hot sauce reviews app.
    <br />
    <br />
    <a href="https://github.com/PabloSgns/Piiquante"><strong>Explore the docs »</strong></a>
    <br />
    <br />
  </p>
</div>



<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
    </li>
    <li>
      <a href="#built-with">Built With</a>
    </li>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
    </li>
    <li><a href="#requested-features">Requested features</a></li>
    <li><a href="#contact">Contact</a></li>
  </ol>
</details>



<!-- ABOUT THE PROJECT -->
## About The Project
<br/>
The frontend code is given to us at he beginning of the project. The goal is to build an secure API in order for the users to signup, login, add their favorites sauces, and like or dislike the products online.

<p align="right">(<a href="#readme-top">back to top</a>)</p>



## Built With

* Javascript
* Node.js
* Express.js
* MongoDB

<p align="right">(<a href="#readme-top">back to top</a>)</p>


<!-- GETTING STARTED -->
## Getting Started

1. You will need to have <a href="https://nodejs.org/en">Node.js</a> installed on your computer.

2. You will also need to get the front code, you can clone the repo, or just downlaod it as .zip
   ```sh
   git clone https://github.com/OpenClassrooms-Student-Center/Web-Developer-P6.git
   ```
   
3. Clone the repo
   ```sh
   git clone https://github.com/PabloSgns/Piiquante.git
   ```
    
4. Go to the folder that contains the backend code and install npm
    ```sh
    npm install
    ```
    
5. Then from the same folder, you can run the server with
    ```sh
    nodemon server
    ```
    
6. Go to the folder that contains the frontend code and install npm
    ```sh
    npm install
    ```
    
7. Then from the same folder, you can compile the code with
    ```sh
    npm start
    ```
    
<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- FEATURES -->
## Requested features

### API Routes

||Endpoints|Body request</br>(if applicable)|Expected response type|Function|
|-|-|-|-|-|
|POST|/api/auth/signup|{ email: string,</br>password: string }|{ message: String }|Hash of the user's password, user added to the database|
|POST|/api/auth/login|{ email: string,</br>password: string }|{ userId: string,</br>token: string }|Verification of user credentials, returns the user id from the database and a signed JSON web token (also containing the user _id).|
|GET|/api/sauces||Array of sauces|Returns an array of all the sauces from the database|
|GET|/api/sauces/:id||Single sauce|Returns the sauce with the providede _id|
|POST|/api/sauces|{ sauce: String,</br>image: File }|{ message: String }</br>Verb|Captures and saves the image, parses the transformed sauce into a string, and saves it to the database by correctly defining its imageUrl. Initializes sauce likes and dislikes to 0 and usersLiked and usersDisliked to empty arrays. Notice that the original request body is empty; when multer is added it returns a string for the request body based on the data submitted with the file.|
|PUT|/api/sauces/:id|EITHER</br>Sauce as JSON OR</br>{ sauce: String,</br>image: File }|{ message: String }|Updates the sauce with the provided id. If an image is uploaded, it is captured and the sauce's imageUrl is updated. If no file is provided, the sauce information is directly in the request body (req.body.name, req.body.heat, etc.). If a file is provided, the sauce transformed into a character string is in req.body.sauce. Note that the original request body is empty; when multer is added it returns a request body string based on the data submitted with the file|
|DELETE|/api/sauces/:id||{ message: String }|Delete the sauce with the provided _id|
|POST|/api/sauces/:id/like|{ userId: String,</br>like: Number }|{ message: String }|Sets the "Like" status for the supplied userId. If like = 1, the user likes the sauce. If like = 0, the user cancels his like or his dislike. If like = -1, the user does not like the sauce. The user ID must be added or removed from the appropriate table. This keeps track of their preferences and prevents them from liking or disliking the same sauce multiple times: a user can only have one value for each sauce. The total number of “Likes” and “Dislikes” is updated with each new rating.|


### Security requirements

* The user's password must be hashed.
* Authentication must be enforced on all required sauce routes.
* Email addresses in the database are unique and one appropriate Mongoose plugin is used to ensure their uniqueness and report errors.
* MongoDB database security (from a service such as MongoDB Atlas) should not prevent the application from launching on an user's machine.
* A Mongoose plugin must ensure the reporting of errors from the database.
* Latest versions of software are used with updated security patches.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- CONTACT -->
## Contact

Author : Pablo Sagnes

You can reach me on <a href="https://www.linkedin.com/in/pablo-sagnes-8068a7143/">Linkedin</a> or by <a href="mailto:sagnes.pablo@gmail.com">email</a>.

<p align="right">(<a href="#readme-top">back to top</a>)</p>
