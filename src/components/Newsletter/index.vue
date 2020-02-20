<template>
    <div class="container newsl_container">
         <h2>Join to our newsletter</h2>
         <div class="form">
             <input type="text" name="" v-model="email">
             <button @click="submitHandler">Subscribe</button>
         </div>
         <div class="error_label" v-if="error != ''">{{ error }}</div>
         <div class="success_label" v-if="success != ''">{{ success}}</div>
         <div class="small">
             <p>
                 Lorem ipsum dolor sit amet consectetur,
                 adipisicing elit. Veniam, quo. Ad soluta 
                 unde perspiciatis, libero doloribus illo?
                 Quas impedit nobis necessitatibus 
                 placeat eius veritatis pariatur dolores 
                 numquam, harum hic eum?
            </p>
         </div>
    </div>   
</template>
<script>
export default {
    data(){
        return{
            email:'',
            error:'',
            success:'' 
        }
    },
    methods:{
        validate(email){
            let valid = [true,'']
            if(!/\S+@\S+\.\S+/.test(email)){
                valid = [false,'Enter a valid email'];
            }
            if(email === ''){
                valid = [false,"it's empty"]
            }
            return valid
        },
        submitHandler(){
            let valid = this.validate(this.email)
            if(valid[0]){
                this.error = '';
                this.addEmail(this.email)
            }else{
                this.error = valid[1]
            }
        },
        addEmail(email){
            this.$http.get(`users.json?orderBy="email"&&equalTo="${email}"`)
            .then( response => {
                if(Object.getOwnPropertyNames(response.data).length === 0){
                    ///
                    this.$http.post('users.json',{email:this.email})
                    .then( response => {
                         this.success = "Thank you !!!"
                    })
                }else{
                    this.success = "Already on the list";
                } 
            });
            this.clearTimeOut()

        },
        clearTimeOut(){
            setTimeout(()=>{
                this.email ='';
                this.success = '';
                this.error = '';
            },3000)
        }
    }
}
</script>
<style scoped>

</style>