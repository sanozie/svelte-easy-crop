<script lang="ts">
  import queryString from 'query-string'
  import Cropper from '../lib'

  let crop = { x: 0, y: 0 }
  let zoom = 1

  const urlArgs = typeof window !== 'undefined' ? queryString.parse(window.location.search) : null
  let image = typeof urlArgs?.img === 'string' ? urlArgs.img : '/images/dog.jpeg' // so we can change the image from our tests
</script>

<Cropper {image} bind:crop bind:zoom on:cropcomplete={e => console.log(e.detail)} />
