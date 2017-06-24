#	INTRODUCTION
Sound exists in space. Sometimes. And NASA has released a series of space sounds via sound cloud. We have abstracted away some of the hassle in accessing these sounds, so that developers can play with the audio files. For example, a useful application would be an automatic filter to identify human voices in these audio files.

As part of testing this API, Below are the scenarios

## PURPOSE OF THIS DOCUMENT
The purpose of this document is put down scenarios to test below API

https://api.nasa.gov/planetary/sounds

This document covers basic scenarios to test the above mentioned API. This Covers Manual and Automated Tests

Given Information:
HTTP REQUEST

GET https://api.nasa.gov/planetary/sounds

QUERY PARAMETERS

Parameter	Type	Default		Description
q		string	None		Search text to filter results
limit		int	10		number of tracks to return
api_key		string	DEMO_KEY	api.nasa.gov key for expanded usage

EXAMPLE 	QUERY

https://api.nasa.gov/planetary/sounds?q=apollo&api_key=DEMO_KEY
#	MANUAL TESTING

#	AUTOMATED TESTING

