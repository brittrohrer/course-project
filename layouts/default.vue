<template>
    <div>
        <header>
            <nav>
                <ul>
                    <li>
                        <NuxtLink to="/home">Home</NuxtLink>
                    </li>
                    <li>
                        <NuxtLink to="/gallery">Gallery</NuxtLink>
                    </li>
                </ul>
            </nav>
        </header>
        <slot />
    </div>
</template>