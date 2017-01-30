require 'rake/clean' # See http://devblog.avdi.org/2014/04/28/rake-part-6-clean-and-clobber/

# Dotfile => Target file (where this will be installed)
DOTFILE_TARGET = {
  "zshrc.local" => "#{Dir.home}/.zshrc.local",
}

# Generate Rake tasks
targets = []
DOTFILE_TARGET.each do |source, target|
  desc "Install #{source} => #{target}"
  file target => source do |task|
    target_dir = File.dirname(target)
    mkdir_p(target_dir) unless File.exists?(target_dir)
    cp source, target
  end

  CLOBBER << target
  targets << target
end

task default: targets
