<template>
    <div>
        <section id="register" class="vh-100">
            <form id="formRegister" @submit.prevent="submitRegister">
                <div class="container py-5 h-100">
                    <div class="row d-flex justify-content-center align-items-center h-100" style="margin-top: 5%">
                        <div class=" col-12 col-md-8 col-lg-6 col-xl-5">
                            <div class="card shadow-2-strong" style="border-radius: 1rem;">
                                <div class="card-body p-5 text-center">
                                    <img src='https://i.ibb.co/yqzp4qT/weathertive-logo.png' style="width:50%;" />
                                    <br>
                                    <br>
                                    <h2 class="mb-5">Register</h2>

                                    <div class="form-outline mb-4">
                                        <label class="form-label" for="regisEmail">Email</label>
                                        <input type="email" id="regisEmail" class="form-control form-control-lg"
                                            placeholder="Input your email" v-model="email">
                                    </div>

                                    <div class="form-outline mb-4">
                                        <label class="form-label" for="regisPassword">Password</label>
                                        <input type="password" id="regisPassword" class="form-control form-control-lg"
                                            placeholder="Input your password" v-model="password">
                                    </div>

                                    <div class="form-outline mb-4">
                                        <label class="form-label" for="regisPhoneNumber">Phone Number</label>
                                        <input type="text" id="regisPhoneNumber" class="form-control form-control-lg"
                                            placeholder="Input your phone number" v-model="phoneNumber">
                                    </div>

                                    <div class="form-outline mb-4">
                                        <label class="form-label" for="regisLocation">Location</label>
                                        <input type="text" id="regisLocation" class="form-control form-control-lg"
                                            placeholder="Input your location" v-model="location">
                                    </div>

                                    <button class="btn btn-secondary btn-lg btn-block rounded-pill" type="submit">Create
                                        your
                                        account</button>

                                    <hr class="my-4">
                                    <p>Already have an account? back to <router-link to="/login" style="color:gray">
                                            <b>login</b>
                                        </router-link>
                                    </p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </form>
        </section>
    </div>
</template>

<script>
import { mapActions } from 'pinia';
import { customStore } from '../stores/store';

export default {
    data() {
        return {
            email: "",
            password: "",
            phoneNumber: "",
            location: "",
        }
    },
    methods: {
        ...mapActions(customStore, ["handleRegister"]),

        //Submit register
        async submitRegister() {
            this.handleRegister(this.email, this.password, this.phoneNumber, this.location)
        },
    },
}
</script>
