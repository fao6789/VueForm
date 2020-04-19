<template>
  <div class="container">
    <form>
      <div class="row">
        <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
          <h1 class="text-center">From Section For Sky Albert</h1>
          <hr />
          <div class="form-group">
            <label for="email">Mail</label>
            <input type="text" id="email" class="form-control" :value="userData.email" @input="userData.email= $event.target.value" />
          </div>
          <div class="form-group">
            <label for="password">Password</label>
            <input
              type="password"
              id="password"
              class="form-control"
              v-model.lazy="userData.password"
            />
          </div>
          <div class="form-group">
            <label for="age">Age</label>
            <input type="number" id="age" class="form-control" v-model="userData.age" />
          </div>
        </div>
      </div>
      <div class="row">
        <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
          <label for="messege">Messege</label>
          <hr />
          <textarea id="Messege" class="form-control" rows="5" v-model="mess"></textarea>
        </div>
      </div>
      <div class="row">
        <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
          <div class="form-group">
            <label for="sendmail">
              <input type="checkbox" id="sendmail" value="SendMail" v-model="sendEmail" />
              SendMail
            </label>
            <label for="sendInfomail">
              <input type="checkbox" id="sendInfomail" value="SendInfoMail" v-model="sendEmail" />
              SendInfoMail
            </label>
            <label for="cutInfomail">
              <input type="checkbox" id="cutInfomail" value="CutInfoMail" v-model="sendEmail" />
              CutInfoMail
            </label>
          </div>
        </div>
      </div>
      <div class="row">
        <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
          <div class="form-group">
            <label for="male">
              <input type="radio" id="male" value="Male" v-model="gender" />
              Male
            </label>
            <label for="female">
              <input type="radio" id="female" value="Female" v-model="gender"/>
              Female
            </label>
          </div>
        </div>
      </div>
      <div class="row">
        <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
          <div class="form-group">
            <label for="priority">
                Priority
                </label>
              <select name="priority" class="form-control">
                <!-- selected: là auto chọn -->
                <option v-for="item in priority" v-bind:key="item" :selected="item=='low'">{{item}}</option>
              </select>
            
            
          </div>
        </div>
      </div>
       <div class="row">
        <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
          <label for="switched">Switched:</label>
          <CustomeContronl v-model="dataSwicth"></CustomeContronl>
        </div>
      </div>
      <div class="row">
        <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
          <div class="form-group">
            <button class="btn btn-primary"
            @click.prevent="Submit()">Submit!</button>
          </div>
        </div>
      </div>
    </form>
    <hr />
    <div class="row" v-if="isSubmit">
      <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
        <div class="panel panel-default">
          <div class="panel-heading">
            <h4>Your Data</h4>
          </div>
          <div class="panel-body">
            <p>Mail: {{userData.email}}</p>
            <p>Password: {{userData.password}}</p>
            <p>Age: {{userData.age}}</p>
            <p style="white-space:pre">Messenger: {{mess}}</p>
            <p>
              <Strong>SendMail?</Strong>
              <ul>
                <li v-for="item in sendEmail" v-bind:key="item">{{item}}</li>
              </ul>
            </p>
            <p>Gender: {{gender}}</p>
            <p>Priority:</p>
            <p>Switched: {{dataSwicth}}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import CustomeContronl from './components/CustomeControl';
export default {
  data() {
    return {
      userData: {
        email: "",
        password: "",
        age: 0
      },
      mess: "",
      sendEmail: [],
      gender:"Male",
      priority:['hight','medium','low'],
      dataSwicth:true,
      isSubmit :false,
    };
  },
  components:{
    CustomeContronl
  },
  methods:{
    Submit(){
      this.isSubmit= true;
    }
  }

};
</script>

<style>
</style>
