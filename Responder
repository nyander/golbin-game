import java.util.Random;
import java.util.ArrayList;
/**
 * The responder class represents a response generator object.
 * It is used to generate an automatic response to the game player,
 * based on specified command that was input.
 * Input is presented to the responder as a word, and based on that
 * word the responder will carry out the command and generate a 
 * String that represents the response.
 *
 * @version    1.0
 * @author     (insert your name here)
 */
public class Responder
{
    private ArrayList<String> descriptions;
    private Random rnd;
    private int totalSticks;
    private int temperature;
    private Location currentLocation;
    
    public Responder()
    {
        resetTemperature();
        descriptions = new ArrayList<String>();
        getDescriptions();
        rnd = new Random();
        currentLocation = new Location(descriptions.get(rnd.nextInt(descriptions.size()))); //this will create a new location which will get a random location entered in the location class
        totalSticks = 0;
    }
    
    /**
     * Generate a response from the input command.
     * 
     * @param command  The command entered by the user
     * @return       A string that should be displayed as the response
     */
    public String generateResponse(String command)
    {
        if(isAlive())
        {
            decreaseTemperature();
            switch(command) // switch statement allows a variable to be tested for equality against a list of values. Each value is called a case, and the variable being switched on is checked for each case.
            { // if the user were to enter any of the following, this is what will happen. 
                case "light": return lightFire() + "\n" + getTemperatureDetail();

                case "move": currentLocation = new Location(descriptions.get(rnd.nextInt(descriptions.size())));
                return "You move to " + look() + "\n" + getTemperatureDetail();

                case "look": return "You are in " + look() + "\n" + getTemperatureDetail();

                case "pick": totalSticks += currentLocation.takeSticks();
                return "you now have " + totalSticks + " sticks." + "\n" + getTemperatureDetail();

                default: return "Command not recognised " + "\n" + getTemperatureDetail();
            } 
        }
        else
        {
            return "You are too cold to do anything " + "\n" + getTemperatureDetail();
        }
    }
    
   private void getDescriptions()
    {
        descriptions.add("a RnB club");
        descriptions.add("a Toronto views from the 6");
        descriptions.add("a party in Jamaica");
        descriptions.add("a home in Ghana");
        descriptions.add("a lonely street in London");
        descriptions.add("a deserted city");
        descriptions.add("a small island");
        descriptions.add("a basketball court");
    }

    private void resetTemperature()
    {
        temperature = 10;
    }

    private String getTemperatureDetail()
    {
        return "The temperature is now " + temperature;
    }

    private String look()
    {
        StringBuffer sb = new StringBuffer();
        sb.append(currentLocation.look());

        return sb.toString();
    }

    
   private void decreaseTemperature()
   {
       temperature --;
       if(!currentLocation.getGoblin().isNice()) //in location, the goblin is not nice, it will reduce the temprature by one
       {temperature --;}
    }
    
    private boolean isAlive ()
    {
        if (temperature > 0)
        {return true;}
        return false;
    }
    
    private String lightFire()
    {
        int amount = totalSticks += currentLocation.takeSticks();
        if (amount >= 5)
        {
            resetTemperature();
            totalSticks = 0;
            return "The fire burns all your sticks bright and warms you.";
        }
        else
       {totalSticks = 0;
           return "The fire goes out quickly because you need five sticks to make a proper fire";
       }
        }
     
    }
   



