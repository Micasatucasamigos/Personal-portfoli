<script setup>

var tablinks = document.getElementsByClassName("tab-links");
var tabcontents = document.getElementsByClassName("tab-contents");

function opentab(tabname){
    for(tablink of tablinks){
        tablink.classList.remove("active-link");
    }
    for(tabcontent of tabcontents){
        tabcontent.classList.remove("active-tab");
    }
    event.currentTarget.classList.add("active-link");
    document.getElementById(tabname).classList.add("active-tab");
}
var sidemeu = document.getElementById("sidemenu");

function openmenu(){
    sidemeu.style.right = "0";
}
function closemenu(){
    sidemeu.style.right = "-200px";
}
const scriptURL = '< add you own link here >' // add your own app script link here
const form = document.forms['submit-to-google-sheet']
const msg = document.getElementById("msg")

form.addEventListener('submit', e => {
  e.preventDefault()
  fetch(scriptURL, { method: 'POST', body: new FormData(form)})
    .then(response => {
        msg.innerHTML = "Message sent successfully"
        setTimeout(function(){
            msg.innerHTML = ""
        },5000)
        form.reset()
    })
    .catch(error => console.error('Error!', error.message))
}
</script>

<template>
    <div id="header">
    <div class="container">
        <nav>
            <img src="images/logo.png" class="logo">
            <ul id="sidemenu">
                <li><a href="#header">Home</a></li>
                <li><a href="#about">About</a></li>
                <!-- <li><a href="#services">Skills</a></li> -->
                <li><a href="#portfolio">Projects</a></li>
                <li><a href="#contact">Contact</a></li>
                <i class="fas fa-times" onclick="closemenu()"></i>
            </ul>
            <i class="fas fa-bars" onclick="openmenu()"></i>
        </nav>
        <div class="header-text">
            <p>Full-Stack Developer</p>
            <h1>Hi, I'm <span>Jaime</span><br>Rodriguez From Houston, TX</h1>
        </div>
    </div>
</div>
<!-- -----------about---------- -->
<div id="about">
    <div class="container">
        <div class="row">
            <div class="about-col-1">
                <img src="images/Professional Headshot.jpg">
            </div>
            <div class="about-col-2">
                <h1 class="sub-title">About Me</h1>
                <p>I am a highly motivated and adaptable Computer Information Systems graduate from the University of Houston, set to complete my Bachelor of Science degree in May 2024. With a solid foundation in database administration and development, information systems analysis and design, and application development, I bring a diverse skill set to the table.</p>

                <div class="tab-titles">
                    <p class="tab-links active-link" onclick="opentab('skills')">Skills</p>
                    <p class="tab-links" onclick="opentab('experience')">Experience</p>
                    <p class="tab-links" onclick="opentab('education')">Education</p>
                </div>
                <div class="tab-contents active-tab" id="skills">
                    <ul>
                        <li><span>HTML/CSS</span><br>Designing Web/App interfaces</li>
                        <li><span>JavaScript</span><br>Building Android/iOS apps</li>
                        <li><span>Python</span><br>Web app Development</li>
                        <li><span>MySQL</span><br>Building Android/iOS apps</li>
                        <li><span>MongoDB</span><br>Building Android/iOS apps</li>
                        <li><span>Vue.js</span><br>Building Android/iOS apps</li>
                        <li><span>Bootstrap</span><br>Building Android/iOS apps</li>
                    </ul>
                </div>
                <div class="tab-contents" id="experience">
                    <ul>
                        <li><span>2021 - Current</span><br>UI/UX Design Training at ET Institute</li>
                        <li><span>2019 - 2021</span><br>Team lead at StarApp LLC.</li>
                        <li><span>2017 - 2019</span><br>UI/UX Design Executive at Coin Digital Ltd.</li>
                        <li><span>2016 - 2017</span><br>Internship at ekart eCommerce.</li>
                    </ul>
                </div>
                <div class="tab-contents" id="education">
                    <ul>
                        <li><span>2024</span><br>University of Houston - Computer Information Systems, B.S.</li>
                    </ul>
                </div>
            </div>
        </div>
    </div>
</div>
<!-- ---------services---------------- -->
<!-- <div id="services">
    <div class="container">
        <h1 class="sub-title">My Services</h1>
        <div class="services-list">
            <div>
                <i class="fas fa-code"></i>
                <h2>Web Design</h2>
                <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed nulla nibh, tincidunt sit amet sapien quis.</p>
                <a href="#">Learn more</a>
            </div>
            <div>
                <i class="fas fa-crop-alt"></i>
                <h2>UI/UX Design</h2>
                <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed nulla nibh, tincidunt sit amet sapien quis.</p>
                <a href="#">Learn more</a>
            </div>
            <div>
                <i class="fab fa-app-store"></i>
                <h2>App Design</h2>
                <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed nulla nibh, tincidunt sit amet sapien quis.</p>
                <a href="#">Learn more</a>
            </div>
        </div>
    </div>
</div> -->
<!-- ----------portfolio------------ -->
<div id="portfolio">
    <div class="container">
        <h1 class="sub-title">My Work</h1>
        <div class="work-list">
            <div class="work">
                <img src="images/work-1.png">
                <div class="layer">
                    <h3>Social Media App</h3>
                    <p>The app connects you yo the talented people around the world. Download it from play store.</p>
                    <a href="#"><i class="fas fa-external-link-alt"></i></a>
                </div>
            </div>
            <div class="work">
                <img src="images/3368 Project.png">
                <div class="layer">
                    <h3>Music App</h3>
                    <p>The app connects you yo the talented people around the world. Download it from play store.</p>
                    <a href="#"><i class="fas fa-external-link-alt"></i></a>
                </div>
            </div>
            <div class="work">
                <img src="images/">
                <div class="layer">
                    <h3>Online Shopping App</h3>
                    <p>The app connects you yo the talented people around the world. Download it from play store.</p>
                    <a href="#"><i class="fas fa-external-link-alt"></i></a>
                </div>
            </div>
        </div>
        <!-- <a href="#" class="btn">See more</a> -->
    </div>
</div>
<!-- ----------contact------------- -->
<div id="contact">
    <div class="container">
        <div class="row">
            <div class="contact-left">
                <h1 class="sub-title">Contact Me</h1>
                <p><i class="fas fa-paper-plane"></i> alexisrodriguez19345@gmail.com</p>
                <p><i class="fas fa-phone-square-alt"></i> (832)275 - 8104</p>
                <div class="social-icons">
                    <a href="https://facebook.com/"><i class="fab fa-facebook"></i></a>
                    <a href=""><i class="fab fa-twitter-square"></i></a>
                    <a href=""><i class="fab fa-instagram"></i></a>
                    <a href=""><i class="fab fa-linkedin"></i></a>
                </div>
                <a href="images/Jaime Rodriguez Resume CIS Grad.pdf" download class="btn btn2">Download CV</a>
            </div>
            <div class="contact-right">
                <form name="submit-to-google-sheet">
                    <input type="text" name="Name" placeholder="Your Name" required>
                    <input type="email" name="Email" placeholder="Your Email" required>
                    <textarea name="Message" rows="6" placeholder="Your Message"></textarea>
                    <button type="submit" class="btn btn2">Submit</button>
                </form>
                <span id="msg"></span>
            </div>
        </div>
    </div>
    <div class="copyright">
        <p>Copyright © Jaime Rodriguez</p>
    </div>
</div>
  <div id="about">
    <div class="container">
        <div class="row">
            <div class="about-col-1">
                <!-- <img src="images/Professional Headshot.jpg"> -->
            </div>
            <div class="about-col-2">
                <h1 class="sub-title">About Me</h1>
                <p>I am a highly motivated and adaptable Computer Information Systems graduate from the University of Houston, set to complete my Bachelor of Science degree in May 2024. With a solid foundation in database administration and development, information systems analysis and design, and application development, I bring a diverse skill set to the table.</p>

                <div class="tab-titles">
                    <p class="tab-links active-link" onclick="opentab('skills')">Skills</p>
                    <p class="tab-links" onclick="opentab('experience')">Experience</p>
                    <p class="tab-links" onclick="opentab('education')">Education</p>
                </div>
                <div class="tab-contents active-tab" id="skills">
                    <ul>
                        <li><span>HTML/CSS</span><br>Designing Web/App interfaces</li>
                        <li><span>JavaScript</span><br>Building Android/iOS apps</li>
                        <li><span>Python</span><br>Web app Development</li>
                        <li><span>MySQL</span><br>Building Android/iOS apps</li>
                        <li><span>MongoDB</span><br>Building Android/iOS apps</li>
                        <li><span>Vue.js</span><br>Building Android/iOS apps</li>
                        <li><span>Bootstrap</span><br>Building Android/iOS apps</li>
                    </ul>
                </div>
                <div class="tab-contents" id="experience">
                    <ul>
                        <li><span>2021 - Current</span><br>UI/UX Design Training at ET Institute</li>
                        <li><span>2019 - 2021</span><br>Team lead at StarApp LLC.</li>
                        <li><span>2017 - 2019</span><br>UI/UX Design Executive at Coin Digital Ltd.</li>
                        <li><span>2016 - 2017</span><br>Internship at ekart eCommerce.</li>
                    </ul>
                </div>
                <div class="tab-contents" id="education">
                    <ul>
                        <li><span>2024</span><br>University of Houston - Computer Information Systems, B.S.</li>
                    </ul>
                </div>
            </div>
        </div>
    </div>
  </div>
</template>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
