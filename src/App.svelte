<script>
	import { scaleLinear } from 'd3-scale'
	import {data} from './data';
	import Bar from './Bar.svelte';
	import CurvedBar from './CurvedBar.svelte';


	const chartStyle = document.createElement("style");
chartStyle.innerHTML = `rect:hover { fill:white; } 
        path:hover {
            fill: none;
            stroke: white;
            stroke-width: 8;
        }
`;
document.getElementsByTagName("head")[0].appendChild(chartStyle);

const widthScale = scaleLinear()
    .domain([0, 500])
	.range([0, 500])
	
</script>

<svelte:head>
	 <link
      href="https://fonts.googleapis.com/css?family=Tomorrow:100,500&display=swap"
      rel="stylesheet"
    />
</svelte:head>
<main>
	<div class="viz">
      <div class="title">
        <!-- title/header content goes here -->
        <h1>
          NUMBER OF NEGRO STUDENTS TAKING <br />THE VARIOUS COURSES OF STUDY
          <br />OFFERED IN GEROGIA SCHOOLS.
        </h1>
      </div>
      <div>
        <!-- main chart -->
        <svg width="745" height="745" id="chart">
          <!-- <g>
            <text x="14" y="25">Business</text>
            <text x="96" y="25">12</text>
            <rect x="120" y="25" height="8" width="8" />
          </g>  -->
     
          <!-- <g>
            
            <text x="14" y="550">Industrial</text>
            <text x="109" y="550">2252</text>
            <path d= "M 163 555 h369 a10 10 0 0,1, 0, 68 H58 a10 10 0 0,0, 0, 68 h220" fill="none" stroke="rgb(179, 156, 136)" stroke-width="8" />
          </g> -->

		  {#each data as item, i}
			
			{#if item['shape']['type'] === 'curvedbar'}
			
				<!-- {console.log('Curved Bar')} -->
				<CurvedBar 
					courseName={item['course']['name']}
					courseCoords = {item['course']['coords']}
					noOfStudents = {item['students']['no']}
					noOfStudentsCoords = {item['students']['coords']}
					shapeCoords = {item['shape']['coords']}
					width = {[widthScale(item['shape']['width'][0]),widthScale(item['shape']['width'][1])]}
				/>

				
			{/if}

			{#if item['shape']['type'] === 'rect'}
				<Bar 

					courseName={item['course']['name']}
					courseCoords = {item['course']['coords']}
					noOfStudents = {item['students']['no']}
					noOfStudentsCoords = {item['students']['coords']}
					shapeCoords = {item['shape']['coords']}
					width = {widthScale(item['shape']['width'])}
				/>
				
			{/if}
      	{/each}
        </svg>
      </div>

	  
</main>

<style>
	h1 {
  font-family: "Tomorrow", sans-serif;
  font-weight: 500;
  font-size: 19px;
  text-align: center;
  word-spacing: 7px;
  line-height: 1.2;
  color: rgb(60, 60, 60);
}

/* overall graph dimensions */
.viz {
  width: 600px;
  background-color: rgb(245, 225, 201);
  padding: 15px;
}

/* graph elements */


	rect {
		fill: rgb(179, 156, 136);
	}

/* footer styling */
	/* .caption {
	width: 250px;
	}

	.plateTitle {
	font-weight: 700;
	margin-right: 10px;
	} */

	p {
	font-family: sans-serif;
	font-size: 12px;
	font-weight: 500;
	}


</style>