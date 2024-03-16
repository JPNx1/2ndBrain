<template>
    <div id="clock">
        <p class="date">It is the {{ date }}</p>
        <p class="time">{{ time }}</p>
    </div>
</template>

<script>
    import { ref } from 'vue'
    export default
    {
        data ()
        {
            return {
                date : 'Current Date',
                time : 'Current Time'
            }
        },
        created()
        {
            this.date = foo()
        }
        
    }

    
</script>