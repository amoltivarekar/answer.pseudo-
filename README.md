# answer.pseudo-

/** Generate random integers in a certain range. */
public final class RandomRange {
  
  public static final void main(String[] a)
  {
    log("Generating random integers in the range 6..20.");
    
    int START = 6;
    int END = 20;
    Random random = new Random();
    
    showRandomInteger(START, END, random);
 
    log("Done.");
  }
  
  private static void showRandomInteger(int aStart, int aEnd, Random aRandom){
    if (aStart > aEnd)
    {
      throw new IllegalArgumentException("Start cannot exceed End.");
    }
    //get the range, casting to long to avoid overflow problems
    long range = (long)aEnd - (long)aStart + 1;
    // compute a fraction of the range, 0 <= frac < range
    long fraction = (long)(range * aRandom.nextDouble());
    int randomNumber =  (int)(fraction + aStart);    
    log("Generated : " + randomNumber);
  }
  
  private static void log(String aMessage){
    System.out.println(aMessage);
  }
} 
