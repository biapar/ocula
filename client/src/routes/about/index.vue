<template>
    <app-layout class="about-route">
        <template #header>
            <div layout="row center-left">
                <icon name="info"/><strong class="margin__left--small">About</strong>
            </div>
        </template>
        <section class="text--centre">
            <img class="about-route__logo" :src="$options.staticData.logo" alt="Ocula">
            <h1>{{ title }}</h1>
            <div>{{ description }}</div>
        </section>
        <block title="Application" class="margin__top--large">
            <div class="about-route__details-grid">
                <strong>Version</strong>
                <div>{{ version }}</div>
                <strong>Author</strong>
                <div>{{ author }}</div>
                <strong>Licence</strong>
                <div>{{ license }}</div>
                <strong>Source</strong>
                <a :href="repository" target="_blank">Github</a>
            </div>
        </block>
        <block title="Credits" class="margin__top--large">
            <div class="about-route__details-grid">
                <strong>Forecast Data</strong>
                <a href="https://darksky.net" target="_blank">DarkSky</a>
                <strong>Maps/Geocoding</strong>
                <a href="https://www.mapbox.com" target="_blank">Mapbox</a>
                <strong>Map Tiles</strong>
                <a href="https://www.rainviewer.com" target="_blank">RainViewer</a>
                <strong>Logo Design</strong>
                <a href="https://github.com/ethanroxburgh" target="_blank">Ethan Roxburgh</a>
                <strong>Icons</strong>
                <a href="https://feathericons.com/" target="_blank">Feather Icons</a>
            </div>
        </block>
        <footer class="margin__top--large text--centre">
            <small class="text--meta">Psalm 147:8</small>
        </footer>
    </app-layout>   
</template>

<script lang="ts">
import Vue from 'vue';

import AppLayout from '../../components/core/layouts/app.vue';

import manifest from '../../../package.json';
import logo from '../../assets/images/ocula-192.svg';

export default Vue.extend({

    data() {
        return manifest;
    },

    // @ts-ignore
    staticData: {
        logo
    },

    components: {
        AppLayout
    }

});
</script>

<style lang="scss">

    .about-route__logo {
        width: 96px;
    }

    .about-route__details-grid {
        display: grid;
        grid-template-columns: auto 1fr;
        grid-gap: var(--spacing__x-small) var(--spacing__small);
    }

</style>