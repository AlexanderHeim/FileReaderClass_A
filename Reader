import java.io.BufferedReader;
import java.io.File;
import java.io.FileNotFoundException;
import java.io.FileReader;
import java.io.IOException;
import java.util.ArrayList;

public class Reader {

	private File file;
	private BufferedReader breader;
	
	public Reader(String filepath) throws IOException {
		this.file = new File(filepath);
		this.breader = new BufferedReader(new FileReader(file));
		this.breader.mark(173741824);
	}
	
	public String getWholeFile() throws IOException {
		return readWholeFile();
	}
	
	public String getLine(int line) throws IOException {
		return readLine(line);
	}
	
	public String[] getWordsInLine(int line, String divider) throws IOException{
		String l = getLine(line);
		String[] words = l.split(divider);
		return words;
	}
	
	private String readWholeFile() throws IOException {
		String st;
		String output = "";
		
		while ((st = breader.readLine()) != null) {
		  output += st + "\n";
		}
		//Remove last \n
		if(output != null && output.length() > 0 && output.charAt(output.length() - 1) == '\n') output = output.substring(0, output.length() - 1);
		breader.reset();
		return output;
	}
	
	private String readLine(int line) throws IOException {
		for(int i = 0; i < line; i++) breader.readLine();
		String out = breader.readLine();
		breader.reset();
		return out;
	}
}
