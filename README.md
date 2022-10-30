# payment
Great repository names are short and memorable. Need inspiration? How about supreme-journey?



const paymentSuccess = true;
const marks = 60;

function enroll() {
    console.log("Course enrollment is in process.");
  
    const promise = new Promise(function(resolve, reject) {
        setTimeout(function() {
            if (paymentSuccess) {
              resolve();
            } else {
              reject("Payment failed!");
            }
          }, 2000)
    });
    return promise;

  }
  
  function progress() {
    console.log("Course on progress...");
  
    const promise = new Promise(function(resolve, reject) {
        setTimeout(function() {
            if (marks >= 80) {
              resolve();
            } else {
              reject("You could not get enough marks to get the certificate!");
            }
          }, 3000)
    });
    return promise
  }
  
  function getCertificate(){
    console.log("Preparing your certificate!");
  
    const promise = new Promise(function(resolve) {
        setTimeout(function() {
            resolve("Congrates! you got the certificate.");
          }, 1000)
    });
    return promise
  }
  enroll()
         .then(progress)
         .then(getCertificate)
         .then(function(value){
            console.log(value);
         })
         .catch(function(err){
            console.log(err);
         });
         
