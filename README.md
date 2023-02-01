# LA1400 

```java
package Marku.Erik;
import robocode.*;

public class TheG020 extends JuniorRobot
{
    int users = others;
    public void run() {

        setColors(black, red, black, red, black);
       
		 while(true)
		 {
         if (users < 3)
		 {
		 defendMode();
		 }
		 else
		 {
		 attackMode();
		 }	
    }
}
 
 public void onScannedRobot() {
	
		turnGunTo(scannedAngle);
		if (users <= 5)
		{
		    bearGunTo(scannedBearing);
			fire(1);
		}
		else if(users >= 20)
		{
            bearGunTo(scannedBearing);
		    fire(3);
		}
		else
		{
		    bearGunTo(scannedBearing);
		    fire(2);
		}
		
		if (scannedDistance < 50)
		{
			fire (3);
		} 
		else if (scannedDistance < 100)
		{
			fire (2.5);
		} 
		else
		{
			fire (1);
		}
	}

    public void onHitRobot()
	{
	   bearGunTo(scannedBearing);
       fire(3);
    }

    public void onHitByBullet()
	{
        turnGunTo(hitByBulletAngle);
        fire(3);
        back(100);
        turnRight(90);
    }
	
    public void isCollision()
	{
        back(100);
        turnRight(90);
    }
   
    public void onHitWall()
	{
	    back(50);
        turnRight(90);
    }  
	public void attackMode()
	{
        ahead(240);
        turnGunRight(360);
        back(80);
        turnGunRight(360);
        ahead(160);
	}  
	public void defendMode()
	{
         back(90);
		 turnLeft(90);   
	}
} 
```
