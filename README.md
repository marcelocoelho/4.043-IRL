# 4.043-IRL


For those that need code to read data from the Arduino, the attached file includes what you need. 

You need to add this in sketch.js, below where you currently have code for connecting to Arduino. (Notice that I repeated the part of the code that makes the connection. You don't need to include that twice). 


```javascript
//initialize serialport with 115200 baudrate.
sp = new serialPort('/dev/tty.usbserial-1410', {
baudRate: 115200,
});

var Readline = serialPort.parsers.Readline;	    // make instance of Readline parser
var parser = new Readline();					        // make a new parser to read ASCII lines
sp.pipe(parser);	

parser.on('data', readSerialData);              // called when there's new data incoming


function readSerialData(data) {    
    
    // add your code to handle arduino incoming data here
    console.log(data);

}
```

