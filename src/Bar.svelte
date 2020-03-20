<script>
    export let courseName;
    export let courseCoords;
    export let noOfStudents;
    export let noOfStudentsCoords;
    export let shapeCoords;
    export let width;
</script>


<g>
    
    <text x="{courseCoords[0]}" y="{courseCoords[1]}">{courseName}</text>
    <text x="{noOfStudentsCoords[0]}" y="{noOfStudentsCoords[1]}">{noOfStudents}</text>
    <rect x="{shapeCoords[0]}" y="{shapeCoords[1]}" height="8" width="{width}" />
</g>
     
<style>
    rect {
	fill: rgb(179, 156, 136);
}


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
