<template>
    <div>
        <nav>
            <div class="container">
                <div>
                    <img alt="Vue logo" src="@/assets/logo.png">
                    <h4>vue-slide-unlock</h4>
                </div>
                <div>
                    <a class="nav-item" href="https://github.com/joseph2/vue-slide-unlock" title="Github" target="_blank">
                        Documentation
                    </a>
                    <a class="nav-item" href="https://github.com/joseph2" title="Github" target="_blank">
                        <div class="nav-icon">
                            <svg viewBox="0 0 16 16">
                                <path d="M7.999,0.431c-4.285,0-7.76,3.474-7.76,7.761 c0,3.428,2.223,6.337,5.307,7.363c0.388,0.071,0.53-0.168,0.53-0.374c0-0.184-0.007-0.672-0.01-1.32 c-2.159,0.469-2.614-1.04-2.614-1.04c-0.353-0.896-0.862-1.135-0.862-1.135c-0.705-0.481,0.053-0.472,0.053-0.472 c0.779,0.055,1.189,0.8,1.189,0.8c0.692,1.186,1.816,0.843,2.258,0.645c0.071-0.502,0.271-0.843,0.493-1.037 C4.86,11.425,3.049,10.76,3.049,7.786c0-0.847,0.302-1.54,0.799-2.082C3.768,5.507,3.501,4.718,3.924,3.65 c0,0,0.652-0.209,2.134,0.796C6.677,4.273,7.34,4.187,8,4.184c0.659,0.003,1.323,0.089,1.943,0.261 c1.482-1.004,2.132-0.796,2.132-0.796c0.423,1.068,0.157,1.857,0.077,2.054c0.497,0.542,0.798,1.235,0.798,2.082 c0,2.981-1.814,3.637-3.543,3.829c0.279,0.24,0.527,0.713,0.527,1.437c0,1.037-0.01,1.874-0.01,2.129 c0,0.208,0.14,0.449,0.534,0.373c3.081-1.028,5.302-3.935,5.302-7.362C15.76,3.906,12.285,0.431,7.999,0.431z" />
                            </svg>
                        </div>
                    </a>
                </div>
            </div>
        </nav>
        <div class="container is-content">
            <section class="head">
                <img class="logo" alt="Vue logo" src="./assets/logo.png">

                <h1>Vue.js slide to unlock component</h1>
                <div class="description">
                    <b>Protect users from accidental clicks for Vue 3.x</b>
                </div>
            </section>

            <section class="demo-section">
                <slide-unlock
                    ref="vueslideunlock"
                    :auto-width="getAutoWidth"
                    :circle="getShape"
                    :disabled="getDisabled"
                    :noanimate="getNoAnimated"
                    :width="width"
                    :height="height"
                    :text="text"
                    :success-text="successText"
                    :handler-icon="handlerIcon"
                    :success-icon="successIcon"
                />
            </section>

            <section class="props-section">
                <h2>Options (props)</h2>

                <div class="grid is-4">
                    <div class="item">
                        <label for="autoWidth">
                            <input
                                id="autoWidth"
                                v-model="autoWidth"
                                type="checkbox"
                                true-value="true"
                                false-value="false"
                            >
                            autoWidth
                        </label>
                    </div>
                    <div class="item">
                        <label for="isCircle">
                            <input
                                id="isCircle"
                                v-model="isCircle"
                                type="checkbox"
                                true-value="true"
                                false-value="false"
                            >
                            isCircle
                        </label>
                    </div>
                    <div class="item">
                        <label for="isDisabled">
                            <input
                                id="isDisabled"
                                v-model="isDisabled"
                                type="checkbox"
                                true-value="true"
                                false-value="false"
                            >
                            isDisabled
                        </label>
                    </div>
                    <div class="item">
                        <label for="isNoAnimate">
                            <input
                                id="isNoAnimate"
                                v-model="isNoAnimate"
                                type="checkbox"
                                true-value="true"
                                false-value="false"
                            >
                            isNoAnimate
                        </label>
                    </div>
                </div>

                <div class="grid">
                    <div class="item">
                        <label>width (px)</label>
                        <input v-model="width" type="number" :disabled="autoWidth === 'true'">
                    </div>
                    <div class="item">
                        <label>height (px)</label>
                        <input v-model="height" type="number">
                    </div>
                    <div class="item">
                        <label>text</label>
                        <input v-model="text" type="text">
                    </div>
                    <div class="item">
                        <label>successText</label>
                        <input v-model="successText" type="text">
                    </div>
                </div>
            </section>
            <section class="size-section">
                <h2>Options (CSS Variables)</h2>
                <div class="grid">
                    <div class="item">
                        <label>textSize</label>
                        <input v-model="textSize" type="text">
                    </div>
                    <div class="item">
                        <label>paddingSize</label>
                        <input v-model="paddingSize" type="text">
                    </div>
                </div>
            </section>
            <section class="colors-section">
                <h2>Colors (CSS Variables)</h2>

                <div class="grid">
                    <div class="item">
                        <label>textColor</label>
                        <input v-model="textColor" type="color">
                    </div>
                    <div class="item">
                        <label>textCompleteColor</label>
                        <input v-model="textCompleteColor" type="color">
                    </div>
                    <div class="item">
                        <label>background</label>
                        <input v-model="background" type="color">
                    </div>
                    <div class="item">
                        <label>progressBarBg</label>
                        <input v-model="progressBarBg" type="color">
                    </div>
                    <div class="item">
                        <label>completedBg</label>
                        <input v-model="completedBg" type="color">
                    </div>
                    <div class="item">
                        <label>handlerBg</label>
                        <input v-model="handlerBg" type="color">
                    </div>
                </div>
            </section>

            <section class="actions-section">
                <h2>Actions</h2>
                <button class="btn" @click="resetComponent()">
                    Reset state
                </button>
            </section>
        </div>
        <footer>
            <div class="container">
                <div> &copy; 2021 Anton Zolotov </div>
                <a href="https://github.com/joseph2">github.com</a>
            </div>
        </footer>
    </div>
</template>

<script>
// import SlideUnlock from "@/components/SlideUnlock"
import SlideUnlock from "../dist/vue-slide-unlock.umd.min.js"

export default {
    name: "App",
    components: {
        SlideUnlock
    },
    data () {
        return {
            autoWidth: "true",
            isCircle: "true",
            isDisabled: "false",
            isNoAnimate: "false",
            handlerIcon: "fa fa-angle-double-right",
            successIcon: "fa fa-check",
            text: "slide to unlock",
            successText: "success",
            width: 400,
            height: 80,
            TextSize: getComputedStyle(document.documentElement).getPropertyValue("--su-size-text"),
            PaddingSize: getComputedStyle(document.documentElement).getPropertyValue("--su-size-padding"),
            Background: getComputedStyle(document.documentElement).getPropertyValue("--su-color-bg"),
            ProgressBarBg: getComputedStyle(document.documentElement).getPropertyValue("--su-color-progress-normal-bg"),
            CompletedBg: getComputedStyle(document.documentElement).getPropertyValue("--su-color-progress-complete-bg"),
            HandlerBg: getComputedStyle(document.documentElement).getPropertyValue("--su-color-handler-bg"),
            TextColor: getComputedStyle(document.documentElement).getPropertyValue("--su-color-text-normal"),
            TextCompleteColor: getComputedStyle(document.documentElement).getPropertyValue("--su-color-text-complete")
        }
    },
    computed: {
        getShape() {
            return this.isCircle === "true"
        },
        getAutoWidth() {
            return this.autoWidth === "true"
        },
        getDisabled() {
            return this.isDisabled === "true"
        },
        getNoAnimated() {
            return this.isNoAnimate === "true"
        },
        textSize: {
            set: function(value) {
                this.TextSize = value
                document.documentElement.style.setProperty("--su-size-text", value)
            },
            get: function() {
                return getComputedStyle(document.documentElement).getPropertyValue("--su-size-text")
            }
        },
        paddingSize: {
            set: function(value) {
                this.PaddingSize = value
                document.documentElement.style.setProperty("--su-size-padding", value)
            },
            get: function() {
                return getComputedStyle(document.documentElement).getPropertyValue("--su-size-padding")
            }
        },
        background: {
            set: function(value) {
                this.Background = value
                document.documentElement.style.setProperty("--su-color-bg", value)
            },
            get: function() {
                return getComputedStyle(document.documentElement).getPropertyValue("--su-color-bg")
            }
        },
        progressBarBg: {
            set: function(value) {
                this.ProgressBarBg = value
                document.documentElement.style.setProperty("--su-color-progress-normal-bg", value)
            },
            get: function() {
                return getComputedStyle(document.documentElement).getPropertyValue("--su-color-progress-normal-bg")
            }
        },
        completedBg: {
            set: function(value) {
                this.CompletedBg = value
                document.documentElement.style.setProperty("--su-color-progress-complete-bg", value)
            },
            get: function() {
                return getComputedStyle(document.documentElement).getPropertyValue("--su-color-progress-complete-bg")
            }
        },
        handlerBg: {
            set: function(value) {
                this.HandlerBg = value
                document.documentElement.style.setProperty("--su-color-handler-bg", value)
            },
            get: function() {
                return getComputedStyle(document.documentElement).getPropertyValue("--su-color-handler-bg")
            }
        },
        textColor: {
            set: function(value) {
                this.TextColor = value
                document.documentElement.style.setProperty("--su-color-text-normal", value)
            },
            get: function() {
                return getComputedStyle(document.documentElement).getPropertyValue("--su-color-text-normal")
            }
        },
        textCompleteColor: {
            set: function(value) {
                this.TextCompleteColor = value
                document.documentElement.style.setProperty("--su-color-text-complete", value)
            },
            get: function() {
                return getComputedStyle(document.documentElement).getPropertyValue("--su-color-text-complete")
            }
        }
    },
    methods: {
        resetComponent() {
            this.$refs.vueslideunlock.reset()
        }
    }
}
</script>

<style lang="scss">

:root {
    --color-bg: #FEFEFE;
    --color-lightestgray: #F7F7F7;
    --color-lightgray: #EAEAEA;
    --color-mediumgray: #C1C6C7;
    --color-gray: #8F989A;
    --color-text: #5A6265;
    --color-theme: #42B983;
}
html,
body,
#app {
    margin-top: 2.5rem;
    background-color: var(--color-bg);
    color: var(--color-text);
    font-family: 'Helvetica neue', Helvetica, Arial, sans-serif;
    text-rendering: optimizeLegibility;
}
.container {
    width: 60rem;
    max-width: 96%;
    margin: 0 auto;
    &.is-content {
        width: 35rem;
    }
}
a {
    transition: color 0.2s ease, border-bottom-color 0.2s ease;
    border: none;
    color: var(--color-theme);
    font-family: inherit;
    line-height: inherit;
    text-decoration: none;
    cursor: pointer;
}
h1,
h2,
h4 {
    margin: 0;
    margin-bottom: 0.5rem;
    color: inherit;
    font-style: normal;
    font-weight: 800;
    letter-spacing: -1px;
    text-rendering: optimizeLegibility;
}
h1 {
    font-size: 1.75rem;
}
h2 {
    font-size: 1.125rem;
}
section {
    margin-bottom: 1rem;
    h1,
    h2 {
        text-align: center;
    }
}

.btn {
    background-color: var(--color-bg);
    border: 1px solid var(--color-text);
    padding: 0.5rem 1.25rem;
    border-radius: 0.25rem;
    color: var(--color-text);
    font-weight: 500;
    font-size: 0.875rem;
    transition: all 0.2s ease;
    &:hover {
        background-color: var(--color-lightestgray);
        border-color: var(--color-theme);
        color: var(--color-theme);
        cursor: pointer;
    }
    &:active {
        background-color: var(--color-theme);
        color: var(--color-bg);
    }
}

.grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    column-gap: 1rem;
    row-gap: 0.5rem;
    &.is-4 {
        grid-template-columns: repeat(4, 1fr);
        padding: 0.5rem 0;
    }
    .item {
        max-width: 100%;
        overflow: hidden;
        label {
            display: block;
            margin-bottom: 0.25rem;
            font-size: 0.875rem;
        }
        input {
            box-sizing: border-box;
        }
        input[type=text],
        input[type=color],
        input[type=number] {
            display: block;
            position: relative;
            width: 100%;
            min-width: 100%;
            max-width: 100%;
            height: 2rem;
            padding: 0.125rem 0.5rem;
            transition: all 0.2s ease;
            border: 1px solid var(--color-lightgray);
            border-radius: 0.25rem;
            background-color: var(--color-bg);
            color: var(--color-gray);
            font-size: 0.75rem;
            line-height: 0.75rem;
            cursor: text;
            &:hover {
                border-color: var(--color-mediumgray);
            }
            &:focus,
            &.focus {
                border-color: var(--color-theme);
                outline: none;
            }
            &:disabled {
                opacity: 1;
                background-color: var(--color-lightestgray);
                cursor: not-allowed;
                &:hover {
                    border-color: var(--color-lightgray);
                }
            }
        }
        input[type=color] {
            padding: 0;
            border: none;
            cursor: pointer;
        }
    }
}
nav,
footer {
    width: 100%;
    background-color: var(--color-bg);
}
nav {
    position: fixed;
    z-index: 5;
    top: 0;
    left: 0;
    height: 50px;
    border-bottom: 1px solid var(--color-lightgray);
    .container {
        display: flex;
        align-items: center;
        justify-content: space-between;
        > div {
            display: flex;
            align-items: center;
        }
    }
    h4 {
        margin: 0;
        font-size: 1rem;
        line-height: 50px;
    }
    img {
        width: 24px;
        height: auto;
        margin-right: 0.5rem;
    }
    .nav-item {
        margin-left: 1rem;
        transition: all 0.3s ease;
        color: var(--color-gray);
        font-size: 12px;
        font-weight: bold;
        &:hover {
            color: var(--color-theme);
        }
    }
    .nav-icon {
        width: 20px;
        height: auto;
        margin-top: 4px;
        transition: all 0.3s ease;
        fill: var(--color-gray);
        &:hover {
            fill: var(--color-theme);
        }
    }
}
footer {
    margin-top: 1rem;
    padding: 1rem 0;
    border-top: 1px solid var(--color-lightgray);
    font-size: 0.875rem;
    line-height: 1.25;
    text-align: center;
    a {
        font-size: 0.75rem;
    }
}
.head {
    text-align: center;
    .logo {
        width: 3rem;
        height: auto;
    }
    .description {
        margin-bottom: 1rem;
    }
}
.demo-section {
    margin: 4rem 0;
}
.actions-section {
    text-align: center;
}
</style>
