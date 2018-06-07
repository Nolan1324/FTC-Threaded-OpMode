# FTC-Threaded-OpMode
A library for FTC Java programming that makes multi threading easy.
## How to install
1. Download and extract this repository
2. Drag the folder `threadopmode` into the `org.firstinspires.ftc.teamcode` package of your `TeamCode` module
## How to use
1. Add the namespace to the top of your program
```
import org.firstinspires.ftc.teamcode.threadopmode.*;
```
2. Have your class extend `ThreadOpMode` rather than `OpMode`
```
public class ExampleOpMode extends ThreadOpMode {
  ...
}
```
3. Override the `mainInit` and `mainLoop` methods
```
@Override
public void mainInit() {

}

@Override
public void mainLoop() {

}
```
3. Add regular `init` code to `mainInit`
4. Create a new thread in `mainInit` using the following template
```
registerThread(new TaskThread(new TaskThread.Actions() {
    @Override
    public void loop() {
        //The loop method should contain loop code
    }
}));
```
5. Repeat this for as many threads as you want to spawn
6. (Optional) add code to the main thread in `mainLoop`
```
@Override
public void mainLoop() {
    //Anything you want to periodically run in the MAIN thread goes here
}
```
