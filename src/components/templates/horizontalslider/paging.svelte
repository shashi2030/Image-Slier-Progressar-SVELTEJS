<script>
    export let sliderData;
    export let currentSlide;
</script>

<style>
.paging{
        text-align:center;
        border:solid 1px rgba(0,0,0,.2);
        padding:10px 0;        
        font-size:20px;
        width:200px;
        border-radius:10px;
        margin:10px auto;
        background: rgb(249,252,247); /* Old browsers */
        background: -moz-linear-gradient(top, rgba(249,252,247,1) 0%, rgba(245,249,240,1) 100%); /* FF3.6-15 */
        background: -webkit-linear-gradient(top, rgba(249,252,247,1) 0%,rgba(245,249,240,1) 100%); /* Chrome10-25,Safari5.1-6 */
        background: linear-gradient(to bottom, rgba(249,252,247,1) 0%,rgba(245,249,240,1) 100%); /* W3C, IE10+, FF16+, Chrome26+, Opera12+, Safari7+ */
        filter: progid:DXImageTransform.Microsoft.gradient( startColorstr='#f9fcf7', endColorstr='#f5f9f0',GradientType=0 ); /* IE6-9 */
    }
    .paging strong{
        font-size:22px;
    }
</style>
<div class="paging"><strong>{currentSlide + 4}</strong>/{sliderData.length}</div>