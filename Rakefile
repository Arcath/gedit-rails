desc "Installs the Plugins"
task :setup do
	user = ENV['USER']
	if user == "root" then
		system("killall gedit")
		system("cp rails.xml /usr/share/mime/packages")
		system("update-mime-database /usr/share/mime")
		system("cp erb.lang /usr/share/gtksourceview-2.0/language-specs/")
		system("cp yaml.lang /usr/share/gtksourceview-2.0/language-specs/")
		unless File.directory? ENV['HOME'] + "/.gnome2/gedit"
			system("mkdir -p ~/.gnome2/gedit")
		end
		system("cp -R snippets ~/.gnome2/gedit/")
		unless File.directory? ENV['HOME'] + "/.gnome2/gedit/plugins"
			system("mkdir -p ~/.gnome2/gedit/plugins")
		end
		system("cp -R plugins/* ~/.gnome2/gedit/plugins/")
	else
		puts "You need to sudo this action"
	end
end
