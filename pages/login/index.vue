<template>
  <v-row align="center" justify="center">
    <v-col cols="12" sm="8" md="8">
      <v-card class="elevation-12">
        <v-window v-model="step">
          <v-window-item :value="1">
            <v-row>
              <v-col cols="12" md="8">
                <v-card-text class="mt-8">
                  <div
                    class="text-center display-1 light-blue--text text--lighten-2"
                  >สมัครสมาชิก สมาคมศิษย์เก่าพณิชยการพระนคร
                  </div>
                  <div
                    class="text-center display-1 light-blue--text text--lighten-2"
                  >THE ASSOCIATION OF BANGKOK COMMERCIAL ALUMNI
                  </div>
                  <v-form
                    ref="formSignin"
                    v-model="validSignin"
                    lazy-validation
                  >
                    <v-text-field
                      label="Username"
                      name="username"
                      prepend-icon="mdi-account"
                      type="text"
                      color="light-blue lighten-2"
                      :rules="usernameRules"
                      v-model="username"
                    />

                    <v-text-field
                      id="password"
                      label="Password"
                      name="password"
                      prepend-icon="mdi-lock"
                      type="password"
                      color="light-blue lighten-2"
                      :rules="passwordRules"
                      v-model="password"
                    />
                  </v-form>
                  <h3 class="text-center mt-4">คุณลืมรหัสผ่านหรือไม่ ?</h3>
                </v-card-text>
                <div class="text-center mb-3">
                  <v-btn rounded color="light-blue lighten-2" dark @click="Signin()">เข้าสู่ระบบ</v-btn>
                  or
                  <nuxt-link to="/">หน้าหลัก</nuxt-link>
                </div>
              </v-col>
              <v-col cols="12" md="4" class="light-blue lighten-2">
                <v-card-text class="white--text mt-12">
                  <h1 class="text-center display-1 mb-6">สวัสดี ชาวสมาคมศิษย์เก่าพณิชยการพระนคร</h1>
                  <div align="center" justify="center">
                    <img src="~static/logo.png" width="150px" />
                  </div>
                </v-card-text>
                <div class="text-center mb-3">
                  <v-btn rounded outlined dark @click="step++">สร้างบัญชี</v-btn>
                </div>
              </v-col>
            </v-row>
          </v-window-item>
          <v-window-item :value="2">
            <v-row class="fill-height">
              <v-col cols="12" md="4" class="light-blue lighten-2">
                <v-card-text class="white--text mt-12">
                  <h1 class="text-center display-1">กลับไปหน้าเข้าสู่ระบบ</h1>
                  <h5
                    class="text-center"
                  >หากต้องการติดต่อกับเราโปรดเข้าสู่ระบบ</h5>
                </v-card-text>
                <div class="text-center">
                  <v-btn rounded outlined dark @click="step--">เข้าสู่ระบบ</v-btn>
                </div>
              </v-col>

              <v-col cols="12" md="8">
                <v-card-text class="mt-8">
                  <h1 class="text-center display-2 light-blue--text text--lighten-2">สร้างบัญชี</h1>
                  <v-form
                    ref="formSignup"
                    v-model="validSignup"
                    lazy-validation
                  >
                    <v-text-field
                      label="ชื่อ-นามสกุล"
                      name="name"
                      prepend-icon="mdi-account-box"
                      type="text"
                      color="light-blue lighten-2"
                      v-model="name"
                      :rules="nameRules"
                    />

                    <v-text-field
                      label="รหัสบัตรประจำตัวประชาชน"
                      name="citizenid"
                      prepend-icon="mdi-passport"
                      type="text"
                      color="light-blue lighten-2"
                      v-model="cardNumber"
                      :rules="cardNumberRules"
                      v-mask="'#####-#######-#'"
                    />

                    <v-text-field
                      label="เบอร์โทร"
                      name="mobile"
                      prepend-icon="mdi-phone"
                      type="text"
                      color="light-blue lighten-2"
                      v-model="tel"
                      :rules="telRules"
                      v-mask="'###-###-####'"
                    />

                    <v-text-field
                      label="Email"
                      name="Email"
                      prepend-icon="mdi-email"
                      type="email"
                      color="light-blue lighten-2"
                      v-model="email"
                      :rules="emailRules"
                    />

                    <v-text-field
                      label="Username"
                      name="username"
                      prepend-icon="mdi-account"
                      type="text"
                      color="light-blue lighten-2"
                      :rules="usernameRules"
                      v-model="username"
                    />

                    <v-text-field
                      id="password"
                      label="Password"
                      name="password"
                      prepend-icon="mdi-lock"
                      type="password"
                      color="light-blue lighten-2"
                      :rules="passwordRules"
                      v-model="password"
                    />
                  </v-form>
                </v-card-text>
                <div class="text-center mb-3">
                  <v-btn rounded color="light-blue lighten-2" dark @click="Signup()">สร้างบัญชี</v-btn>
                </div>
              </v-col>
            </v-row>
          </v-window-item>
        </v-window>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
import formMixin from '~/mixins/formMixin'

export default {
  layout: 'layoutLogin',
  data() {
    return {}
  },
  mixins: [formMixin],
  methods: {
    Signin() {
      if (this.$refs.formSignin.validate()) {
        console.log('formSignin');
      }
    },
    Signup() {
      if (this.$refs.formSignup.validate()) {
        console.log('formSignup');
      }
    }
  }
}
</script>
