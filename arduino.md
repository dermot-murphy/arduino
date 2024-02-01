Run the container:
	docker run -it -v.:/data canembed/arduino
	
Change to the project directory in the container:
	cd /data
	
Create a new config file:
	arduino-cli config init --dest-dir .

Update the locations:
	edit the file ./arduino-cli.yaml such that:
	
	directories:
    data: ./libraries
    downloads: ./downloads
    user: ./boards

Update the index of cores to the latest version:
	arduino-cli core update-index --config-file ./arduino-cli.yaml
		
Find out the list of supported boards:
	arduino-cli core search --config-file ./arduino-cli.yaml
	
Install the board you want to use, for example for the UNO WIFI REV4 :
	arduino-cli core install arduino:renesas_uno --config-file ./arduino-cli.yaml
	
To find out which boards are installed in the project:
	arduino-cli board listall --config-file ./arduino-cli.yaml

arduino-cli board attach -p /dev/tty17 ./test/test.ino --config-file ./arduino-cli.yaml
	
Other useful commands:
  arduino-cli board [command]

Examples:
  # Lists all connected boards.
  arduino-cli board list

Find out the FQBN for all installed boards:
	arduino-cli board listall --config-file ./arduino-cli.yaml
	
Find out which boards are available for installation:
	arduino-cli core search --config-file ./arduino-cli.yaml

Dump the current config:
	arduino-cli config dump --verbose  --config-file ./arduino-cli.yaml
		
Available Commands:
  use the option which each command as needed --config-file ./arduino-cli.yaml
  
  arduino-cli --help            Displays help on commands available
  arduino-cli board attach      Attaches a sketch to a board.
  arduino-cli board details     Print details about a board.
  arduino-cli board list        List connected boards.
  arduino-cli board listall     List all known boards and their corresponding FQBN.
  arduino-cli board search      Search for a board in the Boards Manager.
  arduino-cli cache clean       Delete Boards/Library Manager download cache.
  arduino-cli compile 			Compiles Arduino sketches.
  arduino-cli core download     Downloads one or more cores and corresponding tool dependencies.
  arduino-cli core install      Installs one or more cores and corresponding tool dependencies.
  arduino-cli core list         Shows the list of installed platforms.
  arduino-cli core search       Search for a core in Boards Manager.
  arduino-cli core uninstall    Uninstalls one or more cores and corresponding tool dependencies if no longer used.
  arduino-cli core update-index Updates the index of cores.
  arduino-cli core upgrade      Upgrades one or all installed platforms to the latest version.
  arduino-cli debug check       Check if the given board/programmer combination supports debugging.
  arduino-cli lib deps          Check dependencies status for the specified library.
  arduino-cli lib download      Downloads one or more libraries without installing them.
  arduino-cli lib examples      Shows the list of the examples for libraries.
  arduino-cli lib install       Installs one or more specified libraries into the system.
  arduino-cli lib list          Shows a list of installed libraries.
  arduino-cli lib search        Searches for one or more libraries data.
  arduino-cli lib uninstall     Uninstalls one or more libraries.
  arduino-cli lib update-index  Updates the libraries index.
  arduino-cli lib upgrade       Upgrades installed libraries.  
  arduino-cli outdated          This commands shows a list of installed cores and/or libraries
                                that can be upgraded. If nothing needs to be updated the output is empty.
  arduino-cli sketch archive    Creates a zip file containing all sketch files.
  arduino-cli sketch new        Create a new Sketch	
  arduino-cli update            Updates the index of cores and libraries to the latest versions.
  arduino-cli upload            Upload Arduino sketches. This does NOT compile the sketch prior to upload.
  arduino-cli version           Shows the version number of Arduino CLI which is installed on your system.
  

Running from Ubuntu in the folder which contains subfolder sketch
Subfolder sketch contains sketch.ino  
arduino-cli compile --build-path build --fqbn arduino:renesas_uno:unor4wifi --config-file arduino-cli.yaml --log-file ./logfile.txt --log-level debug sketch/
