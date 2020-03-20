<script>
    export let courseName;
    export let courseCoords;
    export let noOfStudents;
    export let noOfStudentsCoords;
    export let shapeCoords;
    export let width;
</script>
<g>
    {console.log(shapeCoords)}
    <text x="{courseCoords[0]}" y="{courseCoords[1]}">{courseName}</text>
    <text x="{noOfStudentsCoords[0]}" y="{noOfStudentsCoords[1]}">{noOfStudents}</text>
    <path d="{`M ${shapeCoords[0]} ${shapeCoords[1]} h${width[0]} a10 10 0 0,1, 0, 68 H58 a10 10 0 0,0, 0, 68 h${width[1]}`}" fill="none" stroke="rgb(179, 156, 136)" stroke-width="8" />
</g>

<style>
    
rect {
	fill: rgb(179, 156, 136);
}

text {
	font-family: "Tomorrow", sans-serif;
	font-weight: 100;
	font-size: 12px;
	text-transform: uppercase;
	fill: rgb(60, 60, 60);
	dominant-baseline: hanging;
}

rect {
	fill: rgb(179, 156, 136);
}




p {
	font-family: sans-serif;
	font-size: 12px;
	font-weight: 500;
	}

</style>