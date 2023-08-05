# index.html
// DOM _NODES Manipulation
// createElement
// ApeendChild
//remove
//Create H2 tag from javascsript...?
const rootEl = document.getElementById('root')
console.log('ROOT', rootEl)
const heading = document.createElement('h2')
heading.innerHTML = 'this is h2 tag from js'
rootEl.appendChild(heading)
document.getElementById('h1Tag').remove()
document.getElementById('btn').onclick = ()=> {
    // window.open()
    // const url = '/www.google.com'
    // window.location.href = url
    let cnfrm = confirm('Are you from HYD???')
    if (cnfrm) {
        alert('you are from HYD')
    } else {
        alert('u r not frm hyd')
    }
}
//SCREEN
console.log('SCREEN', screen)

//LOCATION
console.log('LOCATION', window.location)
//HISTORY
document.getElementById('history').onclick = ()=> {
    // window.open()
    alert('You clicked back btn')
    history.back()
}
//NAVIGATOR
console.log("NAVIGATOR", navigator)
// POPUP
// alert('Welcome to JS Tutorial')
// const userName = prompt('ENTER Your Name', 'Nothing')
// console.log('USERNAME', userName)
// const cnfrm = confirm('Are you a  SDE??')
// if (cnfrm) {
//     alert('You are SDE')
// } else {
//     alert('You are not a SDE')
// }

// setTimeout(function, milliseconds)
// setTimeout(()=> {
//     alert('this is an alert after 3 sec')
// }, 3000)

// setInterval(function, milliseconds)
const timeEl = document.getElementById('time')
setInterval(()=> {
    const d = new Date().toLocaleString()
    timeEl.innerHTML=d;
}, 1000)
// document.cookie = "username = Adarsh"

const setCookie = (key, value, expairy)=> {
    const d = new Date()
    d.setTime(d.getTime() + (expairy * 24* 60* 60 * 1000))
    const time = "expires= "+d.toUTCString()
    // format => key=value; expires=date; path=/
    const cookieVal =  `${key}= ${value}; ${time}; path=/`
    console.log('COOKIE', cookieVal)
    document.cookie = cookieVal
}
const getCookie = ()=> {
    const cookies = document.cookie
    const myCookie = cookies.split(';').find(val => val.includes('userName'))
    console.log('COOKIE', myCookie)
    if (myCookie) {
        const name = myCookie.split('=')[1]
        alert(`Welcome to ${name}`)
        console.log('MY COKKIE', myCookie)
    } else {
        const myName = prompt('Enter your name', 'User1')
        if (myName){
            setCookie('userName', myName, 3)
        }
    }
}
getCookie()

// Format: => localStorage.setItem(key, JSON.stringify(value))
// Retrive => JSON.parse(localStorage.getItem(key))

localStorage.setItem('MyMobile', 'MI')

const myMobile = localStorage.getItem('MyMobile')
if(myMobile) {
    console.log('LOCAL_STORAGE', myMobile)
}
const obj = {name:'SHIVA', place: 'HYD'}

localStorage.setItem('myDetails', JSON.stringify(obj))

const myDetails = JSON.parse(localStorage.getItem('myDetails'))
if (myDetails) {
    console.log('GET_FROM_LOCAL', myDetails)
}

const property= 'name'

const person = {
    name: 'Naresh',
    age:'25'
}
// Dot natation
person.name;
// Bracket notation 
person['name'] ;

//Dynamic accesing
person[property];

const all=[];
const str=['a','d','a','r','s','h'];
let n=0;
for(let i=0;i<str.length;i++){
    all[n]=str[i];
    n++
}
console.log(all)
=========================================================================================================================================
