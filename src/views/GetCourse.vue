<template>
    <div>
        <!-- <v-btn @click="getCourseList()" color="warning">Click!</v-btn> -->
        <v-expansion-panels>
            <v-expansion-panel v-for="(item,idx) in courses" :key="idx">
                <v-expansion-panel-header>
                    <h3>{{ item.title }}</h3>
                </v-expansion-panel-header>
                <v-expansion-pannel-content>
                    수강기간: {{item.duration}}<br/>
                    최소인원: {{item.minEnrollment}}<br/>
                    최대인원: {{item.maxEnrollment}}<br/>
                    수 강 료: {{itme.unitPrice}}<br/>
                    <v-card-cations>
                        <div class="flex-grow-1">
                        </div>
                        <v-btn text color="warning">선택</v-btn>
                    </v-card-cations>
                </v-expansion-pannel-content>
            <!-- <v-expansion-panel-conent v-for="(item,idx) in courses" :key="idx">
                <div slot="header">
                    <h3>{{ item.title }}</h3>
                </div>
                <v-card>
                </v-card>
            </v-expansion-panel-conent>-->
        </v-expansion-panel> 
        </v-expansion-panels>
    </div>
</template>

<script>
export default {
    data(){
        return {
            courses:[
                {
                    "title":"에휴 힘들다"
                },
                {
                    "title":"대체 뭔소린지..."
                }
            ]
        }    
    },
    methods:{
        getCourseList(){
            this.$axios
            .get("http://13.124.69.97:8080/courses")
            .then(res => {
                console.log(res.data._embedded.course);
                this.courses = res.data_embedded.course;
            })
            .catch(e=>this.console.log(e));
        }
    },
    created(){
        this.getCourseList();
    }
}
</script>

<style>

</style>