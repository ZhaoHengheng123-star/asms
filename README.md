# asms
automobile-sales-management-system 汽车销售管理系统 Python Vue

[中文版README](README_CN.md)
# Brief Introduction
This is a simple Web project designed to cope with Python course design: **front-end separation + cloud container deployment**.

# Main Technology Stack
Front-End：Vue  ElementUI  D2Admin<br>
Back-End：Python   Flask   MySQL<br>
Deploy：docker & docker-compose

# Main Function
1. View all available automobile information and sell them;<br>
2. Display all unsold car information, and provide the function of deleting and modifying information;<br>
3. Input car information;<br>
4. View details of all sold cars;<br>
5. Provide some after-sales analysis data, such as car type analysis.<br>

# What Is Needed
D2Admin frame.<br>
The Node.js and npm environment is required to regenerate the front-end HTML file.<br>
A Linux server with Docker & Docker-Compose.

# How To Use
```
git clone https://github.com/ZhaoHengheng123-star/asms.git
```
Because I did not use the Nginx agent on the front end, the front end interface was the full URL of the server directly accessed, that is, public network IP. So the project didn't work out of the box, the front-end access `IP` needs to be modified. Port 5000 is the default port of Flask.
```javascript
var api = "http://IP:5000/getinfo";
      Axios.post(api, JSON.stringify({ gettype: 0 }), {
        headers: {
          "Content-Type": "application/x-www-form-urlencoded",
          Accept: "application/json"
        }
      })
```
Because the front-end file is generated by `npm run build`, it is not easy to modify. I put the front-end views source code under `demo` folder. Need to put the `demo` folder in the path of D2Admin's `/src/views`, modify `/src/menus/index.js` and `/src/router/router.js` according to the requirements. <br><br>
Then use npm to re-compile after modification. After compiling, a `dist` folder will be generated in the root directory of D2Admin, and everything under this folder will be copied to the project's `nginx/html`.<br><br>
Orchestrate the container and start:
```
docker-compose up -d
```
<br><br>
If it helps you, please give a star support author.
