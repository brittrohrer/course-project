<template>
    <div>
        <header>
            <nav>
                <ul>
                    <li>
                        <NuxtLink to="/home">Home</NuxtLink>
                    </li>
                    <li>
                        <NuxtLink to="/lakes">The Great Lakes</NuxtLink>
                    </li>
                    <li>
                        <NuxtLink to="/activities">Things To Do</NuxtLink>
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