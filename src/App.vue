<script>
export default {
    data() {
        return {
            title: 'User Data',
            greeting: "Hello, World!",
            count: 0,
            show: false,
            rawHtml: "<span>This is a span</span>",
            msg_input: "",
            users: [
                {
                    id: 1,
                    first_name: "Magnum",
                    last_name: "Claiton",
                    email: "mclaiton0@arstechnica.com"
                }, {
                    id: 2,
                    first_name: "Carolann",
                    last_name: "Speir",
                    email: "cspeir1@purevolume.com"
                }, {
                    id: 3,
                    first_name: "Jamie",
                    last_name: "Nestor",
                    email: "jnestor2@canalblog.com"
                }
            ]
        }
    }, methods: {
        filterdata() {
            this.users = this.users.filter((item) => item === 1)
        },
        display() {
            this.show = !this.show
        }
    }
}
</script>

<template>
    <!--  -->
    <h1>{{ title }}</h1>
    <button @click="display">{{(!show) ? "show list" : "hide list"}}</button>

    <!-- v-if, v-for -->
    <ul v-if="show">
        <li :key="user.id" v-for="user in users">
            {{ user.first_name }}
            {{ user.last_name }}
            {{ user.email }}
        </li>
    </ul>

    <!-- v-show -->
    <ol v-if="show">
        <li :key="user.id" v-for="user in users">
            {{ user.first_name }}
            {{ user.last_name }}
            {{ user.email }}
        </li>
    </ol>


    <div class="message">{{ greeting }}</div>

    <button @click="count++">{{ count }}</button>
    <button v-on:click="count++">{{ count }}</button>

    <p>Using text interpolation: {{ rawHtml }}</p>
    <p>Using v-html directive: <span v-html="rawHtml"></span></p>

    <!-- v-model -->
    <p>Message is: {{ msg_input }}</p>
    <input v-model="msg_input" placeholder="enter some text" />


</template>

<style lang="scss">
@import "./styles.scss";
</style>


<!-- <script>
export default {
    data() {
        return {
            greeting: "Hello, World!",
            count: 0,
            rawHtml: "<span>This is a span</span>",
            data: [{ id: 1, name: "electronics" }, { id: 2, name: "furniture" }, { id: 3, name: "food" }],
            nested_data: [{ id: 1, name: "node_modules", children: [{ id: 1, name: "bin" }] }]
        };
    },
};
</script>

<template>
    <div class="message">{{ greeting }}</div>
    <button @click="count++">{{ count }}</button>
    <button v-on:click="count++">{{ count }}</button>
    <p>Using text interpolation: {{ rawHtml }}</p>
    <p>Using v-html directive: <span v-html="rawHtml"></span></p>
    <ol>
        <li v-for="item in data">
            {{ item.name }}
        </li>
    </ol>

    <ul>
        <li v-for="(item, index) in nested_data">
            {{ name }} - {{ index }} {{ item.name }}
        </li>
    </ul>
</template>

<style lang="scss">
@import "./styles.scss";
</style> -->

<!-- Composition API -->

