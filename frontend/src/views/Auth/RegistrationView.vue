<template>
    <v-container>
        <v-row justify="center">
            <v-col cols="12" sm="8" lg="6">
                <v-card class="elevetion-12">
                    <v-toolbar dark color="indigo-accent-4" class="pl-4">
                            Регистрация
                        </v-toolbar>
                    <v-card-text>
                        <v-form v-model="valid" ref="form" lazy-validation>
                            <v-text-field prepend-icon="mdi-account" name="email" label="Email" type="email" v-model="email"
                                :rules="emailRules">
                            </v-text-field>
                            <v-text-field  
                                prepend-icon="mdi-lock" 
                                name="password" 
                                label="Пароль" 
                                type="password" 
                                v-model="password"
                                :rules="passwordRules" 
                                ></v-text-field>
                                <v-text-field  
                                prepend-icon="mdi-lock" 
                            name="confirm-password" 
                                label="Подтверждение пароля" 
                                type="password" 
                                v-model="confirmPassword"
                                :rules="confirmPasswordRules" 
                            ></v-text-field>

                        </v-form>
                    </v-card-text>
                    <v-card-actions>
                        <v-spacer></v-spacer>
                        <v-btn color="light-blue-darken-3"  >Создать аккаунт</v-btn>
                    </v-card-actions>
                </v-card>
            </v-col>
        </v-row>
    </v-container>
</template>
<script>
export default {
    data() {
        return {
            email: "",
            password: "",
            valid: false,
            emailRules: [
                v => !!v || 'E-mail обязателен',
                v => /.+@.+\..+/.test(v) || 'E-mail должен быть действующим'
            ],
            passwordRules: [
                v => !!v || 'Пароль обязателен',
                v => (v && v.length >= 6) || 'Пароль должен быть больше или равен 6 символам'
            ],
            confirmPasswordRules: [
                v => !!v || 'Password is required',
                v => v === this.password || 'Пароли не совпадают'
            ]


        }
    },
    methods: {
        onSubmit() {
            if (this.$refs.form.validate()) {
                const user = {
                    email: this.email,
                    password: this.password
                }
                console.log(user)
            }
        }

    }
}
</script>
