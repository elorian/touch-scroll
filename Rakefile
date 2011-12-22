task :default => [:minify]

desc "Minify"
task :minify do
  begin
    require 'uglifier'
  rescue LoadError => e
    if verbose
      puts "\nYou'll need the 'uglifier' gem for minification. Just run:\n\n"
      puts "  $ gem install uglifier"
      puts "\nand you should be all set.\n\n"
      exit
    end
    return false
  end
  puts "Minifying jquery.lazyload.js with UglifyJS..."
  File.open("touch-scroll.min.js", "w"){|f| f.puts Uglifier.new.compile(File.read("touch-scroll.js"))}
end
