package src;

import java.io.IOException;
import java.net.UnknownHostException;

import src.client.Client;
import src.service.CoreService;

public class Jokenpon {
    
    public static void main(String[] args) throws UnknownHostException, IOException {
        CoreService service = new CoreService();
        int inputClient = service.greeting();
        if(inputClient == 1){
            Client client = new Client();
            client.startConnection("127.0.0.1", 6666);
            client.sendMessage("hello server");         
                service.playWithAnotherPlayer(1, 2);
                 client.sendMessage(".");  
        
        }
        else{
            service.playWithCPU();
        }  
    }
}
