0.8.2
------
#### Enhancements
* Support filtering on request headers.
    - Add ExVCR.Filter.filter_request_header (#71).

0.8.1
------
#### Changes
* Fix warnings when using elixir v1.4 (#65).

0.8.0
------
#### Changes
* Update dependencies.
    - Update httpotion dependency to 3.0 (#63).

#### Enhancements
* Support regexp request_body pattern (#62).

0.7.4
------
#### Changes
* Ensure blacklist header check is case insensitive (#59).

0.7.3
------
#### Enhancements
* Allow matching requests by headers (#56).

#### Changes
* Fix error at [mix vcr] task when cassette directory does not exist (skip instead of raising errors).
    - Running `mix vcr` without custom cassette folder gives annoying message (#49).
* Fix for duplicated/unnecessary directory creation.
    - Fix configuring cassette_library_dir (#50).
* Fix cached status code for ibrowse (#57).

0.7.2
------
#### Enhancements
* Support recording/replaying gzipped response.
    - Gzipped response body (#46).

0.7.1
------
#### Enhancements
* Support config parameters in config.exs (#37).

#### Changes
* Fix wrong request arguments handling for httpc adapter (#38).

0.7.0
------
#### Changes
* Fix handling for response sequence (#35).
    - If recorded cassettes contain multiple HTTP interactions that match a request, the returned responses are now sequenced.
    - It can break the existing cassettes in certain condition. If error occurred, please try re-recording the cassettes.

0.6.1
------
#### Changes
* Fix for Protocol.UndefinedError when using :multipart with :hackney (#34).

0.6.0
------
#### Changes
* Update dependency module versions.

0.5.2
------
#### Enhancements
* Make the return value from use_cassette block available (#17).

#### Changes
* Exclude `:custom` mode from applying `match_requests_on: [:request_body]` by default.
    - Make it only applies to `:stub` mode, as it breaks existing custom cassettes.
* Avoid throwing Argument Error when option contains tuple (#30).

0.5.1
------
#### Enhancements
* Support matching on request body (#22, #29).
    - match_requests_on: [:request_body]

0.5.0
------
#### Changes
* Update HTTPotion and HTTPoison dependencies (#27).
* Put `:optional` option to HTTPoison dependency.

0.4.1
------
#### Enhancements
* Support for POST requests with form-encoded data in the hackney adapter (#25).
* Support for `filter_sensitive_data` for request url (#26).

0.4.0
------
#### Enhancements
* The `use_cassette` with `custom: true` or `:stub` option can now have either string or regexp format (#13).
    - This item involves json format change. In order to use regexp matching, please wrap the string with "~/" prefix and "/" suffix (ex. "~/regexpstring/")
