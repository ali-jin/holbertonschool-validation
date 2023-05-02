build:
	hugo

clean:
	rm -rf dist/*

post:
	hugo new posts/$(POST_NAME).md
	echo "$(POST_TITLE)" >> $(POST_NAME).md