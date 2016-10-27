# lab5
/*
 * To change this license header, choose License Headers in Project Properties.
 * To change this template file, choose Tools | Templates
 * and open the template in the editor.
 */
package filecrawler;

import java.io.*;     // for File
import java.util.*;   // for Scanner
import java.io.FilenameFilter;

/**
 *
 * @author Hamza
 */
public class FileCrawler {

    /**
     * @param args the command line arguments
     * @throws java.io.FileNotFoundException
     */
    static String text;
    public static void main(String[] args) throws IOException {
        // TODO code application logic here
       // int x = 0;
       
        
        Scanner console = new Scanner(System.in);
        System.out.println("Press 1 for searching all Text files ");
        System.out.println("Press 2 for searching specific files path");
        int x = console.nextInt();
        if(x==1){
            
            System.out.println("Word to Search ");
            text = console.next();
            
            allfile();
        }
        
        else if(x==2)
        {
        System.out.print("Directory to crawl? ");
        String directoryName = console.next();
        System.out.println("Enter the file to be searched.. " );
        String name = console.next();
        System.out.println(directoryName);
        File f = new File(directoryName);
        crawl(name,f);
        //allfile(f);
        }

    }
    //  public static void crawl(File f) throws FileNotFoundException{
         public static void crawl(String name,File file)
    {
        File[] list = file.listFiles();
        if(list!=null)
        for (File fil : list)
        {
            if (fil.isDirectory() )
            {
                crawl(name,fil);
              //  System.out.println("i am in if of txt");
            }              
            else if (name.equalsIgnoreCase(fil.getName()))
            {
                System.out.println(fil.getParentFile());
                System.out.println("I am in Else");
                //exit(1);
}
        
    }
         
         
//        public static void word(String s, File myfile){
//            
//        }
    }
         
         public static void allfile() throws IOException{
             System.out.println("I am in file");
             
             File dir = new File("C:\\Program Files");
             String[] children = dir.list();
             if (children == null) {
             System.out.println("does not exist or is not a directory");
                 }
      else {
         for (int i = 0; i < children.length; i++) {
            String filename = children[i];
            if(filename.endsWith(".txt"))
            {
            System.out.println(filename);
            //readfile(text,filename);
            }
         }
         }
         }
//         public static void readfile(String x,String fil) throws FileNotFoundException, IOException
//         {
//            BufferedReader br = null;
//
//		try {
//
//			String sCurrentLine=x;
//
//			br = new BufferedReader(new FileReader(fil));
//
//			while ((sCurrentLine = br.readLine()) != null) {
//				System.out.println(sCurrentLine);
//			}
//
//		} catch (IOException e) {
//			e.printStackTrace();
//		} finally {
//			try {
//				if (br != null)br.close();
//			} catch (IOException ex) {
//				ex.printStackTrace();
//			}
//		}
//
//         }
}

    

