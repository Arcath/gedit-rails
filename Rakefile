desc "Installs the Plugins"
task :setup do
	user = ENV['USER']
	if user == "root" then
		system("killall gedit")
		system("cp rails.xml /usr/share/mime/packages")
		system("update-mime-database /usr/share/mime")
		system("cp erb.lang /usr/share/gtksourceview-2.0/language-specs/")
		system("cp yaml.lang /usr/share/gtksourceview-2.0/language-specs/")
		system("mkdir -p ~/.gnome2/gedit") unless File.directory? ENV['HOME'] + "/.gnome2/gedit"
		system("cp -R snippets ~/.gnome2/gedit/")
		system("mkdir -p ~/.gnome2/gedit/plugins") unless File.directory? ENV['HOME'] + "/.gnome2/gedit/plugins"
		system("cp -R plugins/* ~/.gnome2/gedit/plugins/")
	else
		puts "You need to sudo this action"
	end
end

task :remove do
	user = ENV['USER']
	if user == "root" then
		system("killall gedit")
		system("rm /usr/share/mime/packages/rails.xml")
		system("update-mime-database /usr/share/mime")
		system("rm /usr/share/gtksourceview-2.0/language-specs/erb.lang")
		system("rm /usr/share/gtksourceview-2.0/language-specs/yaml.lang")
		Dir.glob('snippets/').each { |f| system("rm ~/.gnome2/gedit/snippets/#{f}") }
		system("rmdir ~/.gnome2/gedit/snippets")
		Dir.glob('plugins/').each { |f| system("rm -rf ~/.gnome2/gedit/plugins/#{f}") }
		system("rmdir ~/.gnome2/gedit/plugins")
		system("rmdir ~/.gnome2/gedit")
	else
		puts "You need to sudo this action"
	end
end
