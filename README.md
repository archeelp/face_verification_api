<<<<<<< HEAD
# Keras Face Verification System deployed as Flask REST API	

## What
A POST request can be used to integrate face verification in your system.

## POST Request Format

- Add
```
curl -X POST -F image=@sachin1.png 'http://localhost:5000/add?name=sachin'
```
- Verify
```
curl -X POST -F image=@sachin2.png 'http://localhost:5000/verify?name=sachin'
```
Here **name** should be unique to the person like emailid or something and image should be the image file containing the person's face.
## How to RUN 
```
pip install -r requirements.txt
python main2.py
```

## Output Response

### Verify
- First
```
{
	"code":1,
	"message":"Person is verified correctly",
	"score":"0.8051153"
}
```
- Second
```
{
	"code":0,
	"message":"Person is not verified",
	"score":"1.051153"
}
```
- Third
```
{
    "code": -3,
    "message": "Name does not exist in database"
}
```
- Fourth
```
{
	"code":-1,
	"message":"No frontal face detected on picture"
}
```
- Fifth
```
{
	"code":-2,
	"message":"Model could not be loaded"
}
```
*`Score` is the value of the similarity of the face with the registered face. Lower the value of score , means more similarity*
### ADD
- First
```
{
	"code":1,
	"message":"Face added to the database",
}
```
- Second
```
{
	"code":-1,
	"message":"No frontal face detected",
}
