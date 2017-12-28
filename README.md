# Unity-SerialPortUtility

A lightweight and easy-to-use Serial COM library for Unity Game Engine. Mono C# Compiler does not support SerialPort events so I decided to develop our library for Unity.


And here's sample code! :+1:

```C#
public class SerialCommManager : MonoBehaviour {
    ISerialCommunication serialFacade;
    
    // Use this for initialization
    void Start () {
       serialFacade = new SerialCommunicationFacade();
    }
	
   // Update is called once per frame
    void Update () 
    {
		
    }
    public void ConnectSerial()
    {
        serialFacade.Connect();

    }
    public void SendValueFromSerial(string value)
    {
        byte[] buf = System.Text.Encoding.UTF8.GetBytes(value);
        serialFacade.SendMessage(buf);
    }
    public void DisconnectSerial()
    {
        serialFacade.Disconnect();
    }
}
```
