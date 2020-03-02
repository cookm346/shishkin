wget "https://www.wikiart.org/en/App/Painting/PaintingsByArtist?artistUrl=ivan-shishkin&json=2" -O shishkin.json

jq ".[].image" shishkin.json | tr -d \" > links
#jq ".[].title" shishkin.json | tr -d \" > titles
#jq ".[].yearAsString" shishkin.json | tr -d \" > years

for i in {1..521}
do
	url=$(sed "${i}q;d" links)
	url=${url%\!Large.jpg}
	#title=$(sed "${i}q;d" titles)
	#year=$(sed "${i}q;d" years)

	#file_name=$(echo $title-$year | tr ' ' '-')	
	
	cd ./images
	wget $url 
	cd ../

	sleep 5
done

