<script setup lang="ts">
import { links } from '../data/links'
</script>

<template>
    <h1>Bitcoin linkek</h1>
    <div v-for="kategoria in links" class="links">
        <h2 style="margin-top: 40px;">
            {{ kategoria.category }}
        </h2>
        <div name="links-list" class="card py-3 px-4 my-4">
            <div v-for="link in kategoria.items" class="my-2">
                <a :href="link.url" target="_blank" class="link">
                    <h5 class="top minimargin" style="font-size: 18px;">
                        {{ link.name }}
                    </h5>
                </a>
                <p v-if="link.text" class="minimargin" v-html="link.text" />
                <p v-if="link.afftype" class="minimargin">
                    <b>{{ link.afftype }}</b><br />
                    <span class="alert">{{ link.affdetail }}</span>
                </p>
            </div>
        </div>
    </div>
</template>