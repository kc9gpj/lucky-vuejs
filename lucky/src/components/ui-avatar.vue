<template>
  <div class="avatar" v-bind:style="style">
    <table>
      <tr>
        <td v-if="!hasImage">{{label}}</td>
      </tr>
    </table>
  </div>
</template>

<script>
  import 'status-indicator/styles.css'
  export default {
    name: 'Avatar',
    props: {
      label: { type: String, default: '' },
      size: { type: Number, default: 48 },
      radius: { type: Number, default: 50, validator: (value) => value >= 0 && value <= 50 },
      color: { type: String, default: '' },
      image: { type: String, default: '' },
      stateOnline: {type: Boolean, default: false},
      stateOffline: {type: Boolean, default: true}
    },

    computed: {
      style () {
        var fontSize = this.label.length > 2 ? this.size / 3 : this.size / 2
        return {
          'width': this.size + 'px',
          'height': this.size + 'px',
          'border-radius': this.radius + '%',
          'font-size': fontSize + 'px',
          'background-color': this.color === '' ? this.toColor(this.label) : this.color,
          'background-image': this.hasImage ? 'url(' + this.image + ')' : 'none'
          
          
        }
      },

      hasImage () {
        return (this.image !== '')
        
      },
       online () {
        if(this.stateOnline == true){
          return (<status-indicator positive pulse></status-indicator>)
        } 
      },
        offline () {
        if(this.stateOffline == true){
          return (<status-indicator negative pulse></status-indicator>)
        }
      }
    },
     
  }
</script>

<style scoped>
  .avatar {
    display: inline-block;
    background-color: black;
    color: white;
    width: 48px;
    height: 48px;
    font-size: 12px;
    border-radius: 50%;
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
    background-image: none;
  }
  .avatar table {
    width: 100%;
    height: 100%;
    margin: 0;
    padding: 0;
  }
</style>