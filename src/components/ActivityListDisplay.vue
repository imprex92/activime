<template>
<div class="content">
    <div class="listdisplay-container--activitylist">
        <h1>AKTIVITETSLISTA</h1>
        <button class="listdisplay-container--activitylist--addnewbtn" @click="addNewActivity()">LÄGG TILL NY</button>
        <ul>
            <li class="listdisplay-container listdisplay-container--activity" v-for="activity in activitylist" :key="activity.id">
                <p>{{ activity.title }}</p>
                <div class="listdisplay-container--btncontainer"><button class="listdisplay-container--activitylist--changebtn" @click="editActivity(activity.id)"> ÄNDRA </button>
                <button class="listdisplay-container--activitylist--deletebtn" @click="removeActivity(activity.id)"> TA BORT </button></div>
            </li>
        </ul>
    </div>
</div>

</template>

<script>
export default {
    name: 'ActivityListDisplay',
    data: () => ({
        activitylist: [
            { 
                title: 'Lunch',
                id: 1,
                description: 'Laga och ät lunch',
                allowedInterval: {
                    startHour: '10',
                    startMinute: '30',
                    endHour: '13',
                    endMinute: '15'
                },
                pausLength: 45,
                weatherCondition: 3
            }, 
            { 
                title: 'Kaffepaus',
                id: 2,
                description: 'Gå och ta en kaffe',
                allowedInterval: {
                    startHour: '09',
                    startMinute: '15',
                    endHour: '15',
                    endMinute: '15'
                },
                pausLength: 10,
                weatherCondition: 3
            }, 
            { 
                title: 'Stretchpass',
                id: 3,
                description: 'Sträck ordentligt på armar, ben och rygg!',
                allowedInterval: {
                    startHour: '08',
                    startMinute: '15',
                    endHour: '17',
                    endMinute: '15'
                },
                pausLength: 10,
                weatherCondition: 3
            },
            { 
                title: 'Inomhusvandring',
                id: 4,
                description: 'Gå runt inomhus, stanna inte förrän tiden är slut',
                allowedInterval: {
                    startHour: '08',
                    startMinute: '15',
                    endHour: '16',
                    endMinute: '15'
                },
                pausLength: 15,
                weatherCondition: 2
            },
            { 
                title: 'Promenad',
                id: 5,
                description: 'Ta en promenad utomhus',
                allowedInterval: {
                    startHour: '08',
                    startMinute: '15',
                    endHour: '16',
                    endMinute: '15'
                },
                pausLength: 20,
                weatherCondition: 1
            }
        ]
    }),
    methods: {
        removeActivity: (id) => {
            console.log('Ta bort ' + id)
        },
        editActivity: (id) => {
            console.log('Ändra ' + id)
        },
        addNewActivity: () => {
            console.log('Lägg till aktivitet')
        }
        
    }
}
</script>

<style scoped>
* {
    list-style: none;
}
.content {
  margin-top: 5em;
}
ul {
    padding: 0;
}
li {
    margin-top: 2em;
}

p {
    font-size: 2em;
    align-self: center;
}

.listdisplay-container--activitylist {
    max-width: 1000px;
    margin: auto;
    margin-bottom: 6em;
}

.listdisplay-container--btncontainer {
    display: flex;
    align-items: center;
    flex-wrap: wrap;
}

.listdisplay-container {
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-template-rows: auto;
    column-gap: 2em;
    margin-left: 3em;
    margin-right: 3em;
}

button {
  background-color: #77c9d4;
  width: 10em;
  height: 3em;
  border-radius: 20px;
  border: 0em;
  box-shadow: 1px 6px #999;
  font-weight: 600;
  font-size: 18px;
  cursor: pointer;
  margin: 0.5em;
}

</style>