<!--
Copyright 2020 DigitalOcean

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
                        View components
                    </button>
                </div>
            </form>
        </Landing>

        <div v-else>
            <Header title="App Title">
                <template v-slot:description>
                    App Description
                </template>
                <template v-slot:header>
                    <div>
                        <p>
                            <b>Sections:</b>
                            <span><a href="#headers" class="jump-link">Headers</a></span>
                            <span><a href="#typography" class="jump-link">Typography</a></span>
                            <span><a href="#messages" class="jump-link">Messages</a></span>
                            <span><a href="#skeletons" class="jump-link">Skeletons</a></span>
                            <span><a href="#tables" class="jump-link">Tables</a></span>
                            <span><a href="#buttons" class="jump-link">Buttons</a></span>
                            <span><a href="#inputs" class="jump-link">Inputs</a></span>
                            <span><a href="#panels" class="jump-link">Panels</a></span>
                            <span><a href="#bars" class="jump-link">Bars</a></span>
                            <span><a href="#tabs" class="jump-link">Tabs</a></span>
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
                        Do nothing
                    </button>
                </template>
            </Header>

            <div class="main container">
                <div id="headers">
                    <h2>
                        Headers
                        <a href="#headers"><i class="fas fa-link"></i></a>
                    </h2>
                    <hr/>

                    <h1>Header One</h1>
                    <h2>Header Two</h2>
                    <h3>Header Three</h3>
                    <h4>Header Four</h4>
                </div>

                <div id="typography">
                    <h2>
                        Typography
                        <a href="#typography"><i class="fas fa-link"></i></a>
                    </h2>
                    <hr/>

                    <p>Paragraph</p>
                    <p class="has-text-muted">Muted text</p>
                    <p><b>Bold</b> <i>Italic</i></p>
                    <p><ExternalLink text="External link"></ExternalLink></p>
                    <p><a>Normal link</a></p>

                    <p>Text with <code class="slim">slim code</code> inline</p>
                    <pre><code>A block of code</code></pre>

                    <p>
                        <span class="tag">Tag one</span>
                        <span class="tag">Tag two</span>
                        <span class="tag">Tag three</span>
                    </p>
                </div>

                <div id="messages">
                    <h2>
                        Messages
                        <a href="#messages"><i class="fas fa-link"></i></a>
                    </h2>
                    <hr/>

                    <p><a class="button is-primary" @click="modal">View Modal</a></p>

                    <article class="message">
                        <div class="message-header">
                            <p>Message header</p>
                            <button class="delete" aria-label="delete"></button>
                        </div>
                        <div class="message-body">
                            Message body
                        </div>
                    </article>
                </div>

                <div id="skeletons">
                    <h2>
                        Skeletons
                        <a href="#skeletons"><i class="fas fa-link"></i></a>
                    </h2>
                    <hr/>

                    <p>Animated skeletons:</p>
                    <p>
                        <span v-for="_ in 2">
                            <br/>
                            <span v-for="_ in 3" class="data-skeleton skeleton-running"
                                  :style="{ ...getSkeletonStyle(150, 400), display: 'inline-block', marginRight: '0.2em' }">
                            </span>
                        </span>
                    </p>

                    <p>Static skeletons:</p>
                    <p>
                        <span v-for="_ in 2">
                            <br/>
                            <span v-for="_ in 3" class="data-skeleton"
                                  :style="{ ...getSkeletonStyle(150, 400), display: 'inline-block', marginRight: '0.2em' }">
                            </span>
                        </span>
                    </p>
                </div>

                <div id="tables">
                    <h2>
                        Tables
                        <a href="#tables"><i class="fas fa-link"></i></a>
                    </h2>
                    <hr/>

                    <div class="table-container">
                        <table class="table">
                            <thead>
                            <tr>
                                <th>
                                    Column 1
                                </th>
                                <th>
                                    Column 2
                                </th>
                                <th>
                                    Column 3
                                    <i v-tippy title="I need help, please!" class="far fa-question-circle help"></i>
                                </th>
                            </tr>
                            </thead>
                            <tbody>
                            <tr v-for="i in 3">
                                <td v-for="j in 3">
                                    ({{ i }}, {{ j }})
                                </td>
                            </tr>
                            </tbody>
                        </table>
                    </div>
                </div>

                <div id="buttons">
                    <h2>
                        Buttons
                        <a href="#buttons"><i class="fas fa-link"></i></a>
                    </h2>
                    <hr/>

                    <p v-for="item in ['primary', 'link', 'info', 'secondary', 'success', 'warning', 'danger']">
                        <a :class="`button is-${item}`">{{ item }}</a>
                        <a :class="`button is-${item} is-inverted`">{{ item }} inverted</a>
                        <a :class="`button is-${item} is-outline`">{{ item }} outline</a>
                    </p>

                    <p>
                        <a class="button is-small">is-small</a>
                        <a class="button is-mini">is-mini</a>
                        <a class="button is-tiny">is-tiny</a>
                    </p>
                </div>

                <div id="inputs">
                    <h2>
                        Inputs
                        <a href="#inputs"><i class="fas fa-link"></i></a>
                    </h2>
                    <hr/>

                    <div>
                        <p>Main Search:</p>
                        <form autocomplete="on" @submit.prevent="">
                            <div class="input-container">
                                <label for="input_search" class="hidden">Input</label>
                                <i class="fas fa-search"></i>
                                <input id="input_search"
                                       class="input"
                                       type="text"
                                       placeholder="The input"
                                />
                                <button class="button is-primary">
                                    Search
                                </button>
                            </div>
                        </form>
                        <form autocomplete="on" @submit.prevent="">
                            <div class="input-container">
                                <label for="input_search_disabled" class="hidden">Input</label>
                                <i class="fas fa-search"></i>
                                <input id="input_search_disabled"
                                       class="input"
                                       type="text"
                                       placeholder="Disabled input"
                                       disabled
                                />
                                <button class="button is-primary">
                                    Search
                                </button>
                            </div>
                        </form>
                        <form autocomplete="on" @submit.prevent="">
                            <div class="input-container">
                                <label for="input_search_readonly" class="hidden">Input</label>
                                <i class="fas fa-search"></i>
                                <input id="input_search_readonly"
                                       class="input"
                                       type="text"
                                       placeholder="Read only input"
                                       readonly
                                />
                                <button class="button is-primary">
                                    Search
                                </button>
                            </div>
                        </form>
                    </div>

                    <div class="demo-header-search">
                        <p>Header Search:</p>
                        <form autocomplete="on" @submit.prevent="">
                            <div class="input-container">
                                <label for="input_header_search" class="hidden">Input</label>
                                <i class="fas fa-search"></i>
                                <input id="input_header_search"
                                       class="input"
                                       type="text"
                                       placeholder="The input"
                                />
                                <button class="button is-inline">
                                    Search
                                </button>
                            </div>
                        </form>
                        <form autocomplete="on" @submit.prevent="">
                            <div class="input-container">
                                <label for="input_header_search_disabled" class="hidden">Input</label>
                                <i class="fas fa-search"></i>
                                <input id="input_header_search_disabled"
                                       class="input"
                                       type="text"
                                       placeholder="Disabled input"
                                       disabled
                                />
                                <button class="button is-inline">
                                    Search
                                </button>
                            </div>
                        </form>
                        <form autocomplete="on" @submit.prevent="">
                            <div class="input-container">
                                <label for="input_header_search_readonly" class="hidden">Input</label>
                                <i class="fas fa-search"></i>
                                <input id="input_header_search_readonly"
                                       class="input"
                                       type="text"
                                       placeholder="Read only input"
                                       readonly
                                />
                                <button class="button is-inline">
                                    Search
                                </button>
                            </div>
                        </form>
                    </div>
                </div>

                <div id="panels">
                    <h2>
                        Panels
                        <a href="#panels"><i class="fas fa-link"></i></a>
                    </h2>
                    <hr/>

                    <h3>Horizontal panel list, is-selectable &amp; is-droplet</h3>
                    <div class="panel-list">
                        <div class="panel is-selectable is-droplet" v-for="_ in 3">
                            <p><em><sup>$</sup>10<sub> / mo</sub></em></p>
                            <p>Hover over me!</p>
                            <hr/>
                            <p>Fast disk <sub> / SSD magic</sub></p>
                            <p><code>Droplet panel list</code></p>
                        </div>
                    </div>

                    <h3>Vertical panel list, is-droplet &amp; is-focused / is-unfocused</h3>
                    <div class="panel-list panel-list-vertical">
                        <div :class="`panel is-droplet is-${i === 1 ? '' : 'un'}focused`" v-for="i in 3">
                            <p><em><sup>$</sup>10<sub> / mo</sub></em></p>
                            <hr/>
                            <p>Fast disk <sub> / SSD magic</sub></p>
                            <p><code>Vertical droplet panel list</code></p>
                        </div>
                    </div>
                </div>

                <div id="bars">
                    <h2>
                        Bars
                        <a href="#bars"><i class="fas fa-link"></i></a>
                    </h2>
                    <hr/>

                    <div class="bars">
                        <div class="bar is-primary" style="width: 75%;"></div>
                        <div class="bar is-dark" style="width: 40%;"></div>
                    </div>

                    <br/>

                    <div class="bars">
                        <div class="bar-stack">
                            <div class="bar is-primary" style="width: 70%;"></div>
                            <div class="bar is-dark" style="width: 20%;"></div>
                        </div>
                        <div class="bar-stack">
                            <div class="bar is-primary" style="width: 4%;"></div>
                            <div class="bar is-dark" style="width: 6%;"></div>
                            <div class="bar is-primary" style="width: 10%;"></div>
                            <div class="bar is-dark" style="width: 20%;"></div>
                        </div>
                    </div>
                </div>

                <div id="tabs">
                    <h2>
                        Tabs
                        <a href="#tabs"><i class="fas fa-link"></i></a>
                    </h2>
                    <hr/>

                    <div class="tabs">
                        <ul>
                            <li class="is-active">
                                <a>Hello</a>
                            </li>
                            <li>
                                <a>World</a>
                            </li>
                            <li>
                                <a>do-bulma Tabs</a>
                            </li>
                            <li>
                                <a>Tabulated Content</a>
                            </li>
                        </ul>
                    </div>
                </div>
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
    import ExternalLink from "do-vue/src/templates/external_link"
    import { getSkeletonStyle } from "../../src/utils/skeletonStyle"
    import VueTippy from "vue-tippy"
    import Vue from "vue"

    Vue.use(VueTippy)

    export default {
        name: "App",
        components: {
            Landing,
            Header,
            Modal,
            ExternalLink,
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
            getSkeletonStyle,
        },
        mounted() {
            if (window.location.hash) {
                this.$data.landing = false;
            }
        },
    }
</script>
