<template>
<section>
  <div class="overlay"></div>
  <div class="gtco-container">
    <div class="row">
      <div class="col-md-12 col-md-offset-0 text-left">


        <div class="row row-mt-15em">
          <div class="col-md-7 mt-text animate-box" data-animate-effect="fadeInUp">
            <h1>Planing Trip To Anywhere in The World?</h1>
            <li id="textMessage"></li>
          </div>
          <div class="col-md-4 col-md-push-1 animate-box" data-animate-effect="fadeInRight">
            <div class="form-wrap">
              <div class="tab">

                <div class="tab-content">
                  <div class="tab-content-inner active" data-content="signup">
                    <h3>Book Your Trip</h3>
                    <form action="#">
                      <div class="row form-group">
                        <div class="col-md-12">
                          <label for="fullname">Your Name</label>
                          <input type="text" id="fullname" class="form-control">
                        </div>
                      </div>
                      <div class="row form-group">
                        <div class="col-md-12">
                          <label for="activities">Activities</label>
                          <select name="#" id="activities" class="form-control">
                          <option value="0">Activities</option>
                          <option value="1">Hiking</option>
                          <option value="2">Caving</option>
                          <option value="3">Swimming</option>
                        </select>
                        </div>
                      </div>
                      <div class="row form-group">
                        <div class="col-md-12">
                          <label for="destination">Destination</label>
                          <select name="#" id="destination" class="form-control">
                          <option value="0">China</option>
                          <option value="1">USA</option>
                          <option value="2">Australia</option>
                          <option value="3">Japan</option>
                        </select>
                        </div>
                      </div>

                      <div class="row form-group">
                        <div class="col-md-12">
                          <label for="date-start">Date Travel</label>
                          <input type="text" id="date-start" class="form-control">
                        </div>
                      </div>

                      <div class="row form-group">
                        <div class="col-md-12">
                          <input type="submit" class="btn btn-primary btn-block" value="Submit" id="btnChangeData">
                        </div>
                      </div>
                    </form>
                  </div>


                </div>
              </div>
            </div>
          </div>
        </div>


      </div>
    </div>
  </div>
</section>
</template>

<script src="https://www.gstatic.com/firebasejs/4.12.1/firebase.js"></script>
<script>
  // Initialize Firebase
  var config = {
    apiKey: "AIzaSyBJxdn4gLGgzB75UEtwE6v40getEavGRHk",
    authDomain: "myfirstfirebase-9ca76.firebaseapp.com",
    databaseURL: "https://myfirstfirebase-9ca76.firebaseio.com",
    projectId: "myfirstfirebase-9ca76",
    storageBucket: "myfirstfirebase-9ca76.appspot.com",
    messagingSenderId: "512131380083"
  };
  firebase.initializeApp(config);
</script>
<script>
var db = firebase.database();
var chatLogin = db.ref("/chat/login");
//DB内容が変更されたとき実行される
chatLogin.on("value", function(snapshot) {
  document.getElementById("textMessage").innerText = snapshot.val().fullname;
});
//入力内容を更新した時
var changeData = function(){
  var fullname = document.getElementById("fullname").value;
  var activities = document.getElementById("activities").value;
  var destination = document.getElementById("destination").value;
  var dateStart = document.getElementById("date-start").value;
  chatLogin.set({fullname:fullname});
  chatLogin.set({activities:activities});
  chatLogin.set({destination:destination});
  chatLogin.set({dateStart:dateStart});
}
//htmlロードが完了したらボタンにイベントを設定
window.onload = function() {
 document.getElementById("btnChangeData").onclick = changeData;
};
</script>
