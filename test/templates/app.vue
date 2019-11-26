<!--
Copyright 2019 DigitalOcean

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
-->

<template>
    <div class="all do-bulma">
        <Landing
            v-if="landing"
            title="App Title"
            description="App Description"
            background-top=""
            background-bottom=""
        >
            <form autocomplete="on" @submit.prevent="toggle">
                <div class="input-container">
                    <label for="input" class="hidden">Input</label>
                    <i class="fas fa-search"></i>
                    <input id="input"
                           class="input"
                           type="text"
                           placeholder="The input"
                    />
                    <button class="button is-primary">
                        Go
                    </button>
                </div>
            </form>
        </Landing>

        <div v-else>
            <Header title="App Title" @form-event="modal">
                <template v-slot:description>
                    App Description
                </template>
                <template v-slot:header>
                    <div>
                        <p>
                            <b>Header Text:</b>
                            <span><a href="#" class="jump-link">Link</a></span>
                            <span><a href="#" class="jump-link">Link</a></span>
                            <span><a href="#" class="jump-link">Link</a></span>
                        </p>
                    </div>
                </template>
                <template v-slot:buttons>
                    <a class="button is-primary" @click="toggle">
                        Back to Landing
                    </a>
                </template>
                <template v-slot:input>
                    <label for="input" class="hidden">Input</label>
                    <i class="fas fa-search"></i>
                    <input id="input"
                           class="input"
                           type="text"
                           placeholder="The input"
                    />
                    <button class="button is-inline">
                        Show Modal
                    </button>
                </template>
            </Header>

            <div class="main container">

            </div>

            <Modal ref="Modal" title="Modal title">
                <p>Modal content</p>
            </Modal>
        </div>
    </div>
</template>

<script>
    import Landing from "do-vue/src/templates/landing"
    import Header from "do-vue/src/templates/header"
    import Modal from "do-vue/src/templates/modal"

    export default {
        name: "App",
        components: {
            Landing,
            Header,
            Modal,
        },
        data() {
            return {
                landing: true,
            }
        },
        methods: {
            toggle() {
                this.$data.landing = !this.$data.landing
            },
            modal() {
                this.$refs.Modal.open()
            },
        }
    }
</script>
