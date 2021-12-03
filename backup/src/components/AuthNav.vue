<template>
  <div class="navbar-nav ml-auto">
    <AuthenticationButton />
	<div> {{  curr_auth  }}</div>
  </div>
</template>

<script>
  import AuthenticationButton from '@/components/AuthenticationButton';

  export default {
	data(){
		return {
			curr_auth:""
		}
	},
    name: 'AuthNav',
    components: { AuthenticationButton },
  
    async created () {
		this.curr_auth=await this.$auth.getTokenSilently();
		console.log(this.curr_auth);
		},
	
	}
</script>