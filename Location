import java.util.Random;
/**
 * Write a description of class Location here.
 * 
 * @author (your name) 
 * @version (a version number or a date)
 */
public class Location
{
    // instance variables - replace the example below with your own
    private int numOfSticks;
    private String description;
    private Goblin goblin;
    private Random rnd; 

    /**
     * Constructor for objects of class Location
     */
    public Location(String describe)//this parameter is the description
    {
        description = describe;
        rnd = new Random();
        numOfSticks = rnd.nextInt(6);
        goblin = new Goblin();
    }
    
    public Goblin getGoblin()
    {
        return goblin;
    }
    
    public int takeSticks()
    {
        int stickAmount = numOfSticks;
        numOfSticks = 0;
        return stickAmount;
    }
    
    public String look ()
    {
        StringBuffer sb = new StringBuffer();
        //tto reutn text and allow string buffer so the follosing
        sb.append(description + "\n");
        sb.append("There are " + numOfSticks + " sitcks here \n");
        sb.append("There is a " + goblin.getDescription() + " here");
        
        if (goblin.isNice() == true)
         { int numOfdonated = goblin.doante(numOfSticks);
           if (numOfdonated > 0)
            {
            numOfSticks = numOfSticks + numOfdonated; // if the amount donated is more than 0, it will add the amount 
                                                            // donated to the amount of sticks useralready has
            sb.append("\n" + "Goblin donated " + numOfdonated + " sticks. Now you have " + numOfSticks + " sticks");}
            }
           else if ( goblin.steals() == true) // if the goblin stals, it will set the numbe of sticks to 0
           {
               numOfSticks = 0;
               sb.append("\n" + "Oh no! The Goblin has stolen the sticks");
            }
            else
            {sb.append("");}
        return sb.toString();
    }
}
