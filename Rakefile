require 'html-proofer'

task test: %i[test_workflows html_proofer]

task :html_proofer do
  sh 'bundle exec jekyll build --future'
  options = {
    assume_extension: true,
    cache: { timeframe: '4w' },
    # check_html: true, # Problem with theme nav
    check_external_hash: true,
    check_img_http: true,
    check_sri: true,
    enforce_https: true,
    http_status_ignore: [403], # All About Cookies returns 403
    parallel: { in_processes: 3 },
    url_ignore: [
      'http://www.andconf.io/', # Their SSL certificate no longer works
    ]
  }
  proofer = HTMLProofer.check_directory('./_site', options)

  proofer.before_request do |request|
    if request.base_url.start_with?('https://twitter.com')
      # Twitter responds with a 400 if it thinks you have an unsupported browser
      request.options[:headers]['User-Agent'] = 'Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_6) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/14.0.1 Safari/605.1.15'
    end
  end

  proofer.run
end

task :test_workflows do
  Dir['.github/workflows/*.yml'].each do |file|
    puts "Checking #{file}"
    YAML.load_file file
  end
end
