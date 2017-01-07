require 'rake/clean'

SOURCE_FILES_TO_INSTALL = [
  "zshrc.local"
]

targets = []

SOURCE_FILES_TO_INSTALL.each do |source|
  target = File.join(Dir.home, ".#{source}")

  desc "Install #{target}"
  file target => source do
    cp source, target
  end

  CLOBBER << target
  targets << target
end

task default: targets
