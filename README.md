谁写哪个章节，大家把自己名字在下面直接标记一下自己网名+日期。

```
* [Name](#name)     ->      * [Name 某某 2015.8.4](doc/name.md)
```

章节写好后，存放到`doc`目录下。章节命名用具体小节的锚点名称。例如`Code Repository`章节，存放路径就应是`doc/code-repository.md`。

有任何疑问，可以随时联系我。翻译交流QQ群：435558580 。

Table of Contents
=================

* [Name yuansheng-8.4](doc/name.md)
* [Status yuansheng-8.6](doc/status.md)
* [Version](#version)
* [Synopsis yuansheng-8.6](doc/synopsis.md)
* [Description](#description)
* [Typical Uses](#typical-uses)
* [Nginx Compatibility](#nginx-compatibility)
* [Installation](#installation)
    * [C Macro Configurations](#c-macro-configurations)
    * [Installation on Ubuntu 11.10](#installation-on-ubuntu-1110)
* [Community](#community)
    * [English Mailing List](#english-mailing-list)
    * [Chinese Mailing List](#chinese-mailing-list)
* [Code Repository](#code-repository)
* [Bugs and Patches](#bugs-and-patches)
* [Lua/LuaJIT bytecode support](#lualuajit-bytecode-support)
* [System Environment Variable Support](#system-environment-variable-support)
* [HTTP 1.0 support lance-2015.8.13](doc/http-10-support.md)
* [Statically Linking Pure Lua Modules](#statically-linking-pure-lua-modules)
* [Nginx Worker内的数据共享 lance-2015.8.5](doc/data-sharing-within-an-nginx-worker.md)
* [Known Issues](#known-issues)
    * [TCP socket connect operation issues](#tcp-socket-connect-operation-issues)
    * [Lua Coroutine Yielding/Resuming](#lua-coroutine-yieldingresuming)
    * [Lua Variable Scope](#lua-variable-scope)
    * [Locations Configured by Subrequest Directives of Other Modules lance-2015.8.12](doc/locations-configured-by-subrequest-directives-of-other-modules.md)
    * [Cosockets Not Available Everywhere](#cosockets-not-available-everywhere)
    * [特别转义序列 lance-2015.8.5](doc/special-escaping-sequences.md)
    * [Mixing with SSI Not Supported](#mixing-with-ssi-not-supported)
    * [SPDY Mode Not Fully Supported](#spdy-mode-not-fully-supported)
    * [Missing data on short circuited requests](#missing-data-on-short-circuited-requests)
* [TODO](#todo)
* [Changes](#changes)
* [Test Suite](#test-suite)
* [Copyright and License](#copyright-and-license)
* [See Also](#see-also)
* [Directives](#directives)
* [Nginx API for Lua](#nginx-api-for-lua)
* [Obsolete Sections](#obsolete-sections)
    * [Special PCRE Sequences](#special-pcre-sequences)

Directives
==========

* [lua_use_default_type 孙晓辉 2015.8.5](doc/lua-use-default-type.md)
* [lua_code_cache 孙晓辉 2015.8.5](doc/lua-code-cache.md)
* [lua_regex_cache_max_entries](#lua_regex_cache_max_entries)
* [lua_regex_match_limit](#lua_regex_match_limit)
* [lua_package_path](#lua_package_path)
* [lua_package_cpath](#lua_package_cpath)
* [init_by_lua](#init_by_lua)
* [init_by_lua_file](#init_by_lua_file)
* [init_worker_by_lua](#init_worker_by_lua)
* [init_worker_by_lua_file](#init_worker_by_lua_file)
* [set_by_lua](#set_by_lua)
* [set_by_lua_file](#set_by_lua_file)
* [content_by_lua dengshiyong 2015.8.12](doc/content_by_lua.md)
* [content_by_lua_file](#content_by_lua_file)
* [rewrite_by_lua](#rewrite_by_lua)
* [rewrite_by_lua_file](#rewrite_by_lua_file)
* [access_by_lua](#access_by_lua)
* [access_by_lua_file](#access_by_lua_file)
* [header_filter_by_lua](#header_filter_by_lua)
* [header_filter_by_lua_file](#header_filter_by_lua_file)
* [body_filter_by_lua](#body_filter_by_lua)
* [body_filter_by_lua_file](#body_filter_by_lua_file)
* [log_by_lua](#log_by_lua)
* [log_by_lua_file](#log_by_lua_file)
* [lua_need_request_body](#lua_need_request_body)
* [lua_shared_dict](#lua_shared_dict)
* [lua_socket_connect_timeout](#lua_socket_connect_timeout)
* [lua_socket_send_timeout](#lua_socket_send_timeout)
* [lua_socket_send_lowat](#lua_socket_send_lowat)
* [lua_socket_read_timeout](#lua_socket_read_timeout)
* [lua_socket_buffer_size](#lua_socket_buffer_size)
* [lua_socket_pool_size](#lua_socket_pool_size)
* [lua_socket_keepalive_timeout](#lua_socket_keepalive_timeout)
* [lua_socket_log_errors](#lua_socket_log_errors)
* [lua_ssl_ciphers](#lua_ssl_ciphers)
* [lua_ssl_crl](#lua_ssl_crl)
* [lua_ssl_protocols](#lua_ssl_protocols)
* [lua_ssl_trusted_certificate](#lua_ssl_trusted_certificate)
* [lua_ssl_verify_depth](#lua_ssl_verify_depth)
* [lua_http10_buffering](#lua_http10_buffering)
* [rewrite_by_lua_no_postpone](#rewrite_by_lua_no_postpone)
* [lua_transform_underscores_in_response_headers](#lua_transform_underscores_in_response_headers)
* [lua_check_client_abort](#lua_check_client_abort)
* [lua_max_pending_timers](#lua_max_pending_timers)
* [lua_max_running_timers](#lua_max_running_timers)

Nginx API for Lua
=================

* [Introduction](#introduction)
* [ngx.arg](#ngxarg)
* [ngx.var.VARIABLE](#ngxvarvariable)
* [Core constants lance-2015.8.14](doc/core-constants.md)
* [HTTP method constants lance-2015.8.13](doc/http-method-constants.md)
* [HTTP status constants lance-2015.8.13](doc/http-status-constants.md)
* [Nginx log level constants lance-2015.8.13](doc/nginx-log-level-constants.md)
* [print lance-2015.8.14](doc/print.md)
* [ngx.ctx lance-2015.8.14](doc/ngxctx.md)
* [ngx.location.capture lance-2015.8.11](doc/ngxlocationcapture.md)
* [ngx.location.capture_multi lance-2015.8.11](doc/ngxlocationcapture_multi.md)
* [ngx.status](#ngxstatus)
* [ngx.header.HEADER](#ngxheaderheader)
* [ngx.resp.get_headers](#ngxrespget_headers)
* [ngx.req.start_time](#ngxreqstart_time)
* [ngx.req.http_version](#ngxreqhttp_version)
* [ngx.req.raw_header](#ngxreqraw_header)
* [ngx.req.get_method](#ngxreqget_method)
* [ngx.req.set_method](#ngxreqset_method)
* [ngx.req.set_uri](#ngxreqset_uri)
* [ngx.req.set_uri_args](#ngxreqset_uri_args)
* [ngx.req.get_uri_args](#ngxreqget_uri_args)
* [ngx.req.get_post_args](#ngxreqget_post_args)
* [ngx.req.get_headers](#ngxreqget_headers)
* [ngx.req.set_header](#ngxreqset_header)
* [ngx.req.clear_header](#ngxreqclear_header)
* [ngx.req.read_body](#ngxreqread_body)
* [ngx.req.discard_body](#ngxreqdiscard_body)
* [ngx.req.get_body_data](#ngxreqget_body_data)
* [ngx.req.get_body_file](#ngxreqget_body_file)
* [ngx.req.set_body_data](#ngxreqset_body_data)
* [ngx.req.set_body_file](#ngxreqset_body_file)
* [ngx.req.init_body](#ngxreqinit_body)
* [ngx.req.append_body](#ngxreqappend_body)
* [ngx.req.finish_body](#ngxreqfinish_body)
* [ngx.req.socket](#ngxreqsocket)
* [ngx.exec](#ngxexec)
* [ngx.redirect](#ngxredirect)
* [ngx.send_headers](#ngxsend_headers)
* [ngx.headers_sent](#ngxheaders_sent)
* [ngx.print lance-2015.8.7](doc/ngxprint.md)
* [ngx.say lance-2015.8.7](doc/ngxsay.md)
* [ngx.log lance-2015.8.13](doc/ngxlog.md)
* [ngx.flush lance-2015.8.13](doc/ngxflush.md)
* [ngx.exit lance-2015.8.13](doc/ngxexit.md)
* [ngx.eof](#ngxeof)
* [ngx.sleep](#ngxsleep)
* [ngx.escape_uri](#ngxescape_uri)
* [ngx.unescape_uri](#ngxunescape_uri)
* [ngx.encode_args](#ngxencode_args)
* [ngx.decode_args](#ngxdecode_args)
* [ngx.encode_base64](#ngxencode_base64)
* [ngx.decode_base64](#ngxdecode_base64)
* [ngx.crc32_short](#ngxcrc32_short)
* [ngx.crc32_long](#ngxcrc32_long)
* [ngx.hmac_sha1](#ngxhmac_sha1)
* [ngx.md5](#ngxmd5)
* [ngx.md5_bin](#ngxmd5_bin)
* [ngx.sha1_bin](#ngxsha1_bin)
* [ngx.quote_sql_str](#ngxquote_sql_str)
* [ngx.today bells-2015.8.8](doc/ngxtoday.md)
* [ngx.time](#ngxtime)
* [ngx.now](#ngxnow)
* [ngx.update_time bells-2015.8.16](doc/ngxupdate_time.md)
* [ngx.localtime](#ngxlocaltime)
* [ngx.utctime](#ngxutctime)
* [ngx.cookie_time](#ngxcookie_time)
* [ngx.http_time](#ngxhttp_time)
* [ngx.parse_http_time](#ngxparse_http_time)
* [ngx.is_subrequest](#ngxis_subrequest)
* [ngx.re.match lance-2015.8.6](doc/ngxrematch.md)
* [ngx.re.find lance-2015.8.6](doc/ngxrefind.md)
* [ngx.re.gmatch lance-2015.8.6](doc/ngxregmatch.md)
* [ngx.re.sub lance-2015.8.6](doc/ngxresub.md)
* [ngx.re.gsub lance-2015.8.6](doc/ngxregsub.md)
* [ngx.shared.DICT lance-2015.8.10](doc/ngxshareddict.md)
* [ngx.shared.DICT.get lance-2015.8.10](doc/ngxshareddictget.md)
* [ngx.shared.DICT.get_stale lance-2015.8.10](doc/ngxshareddictget_stale.md)
* [ngx.shared.DICT.set lance-2015.8.10](doc/ngxshareddictset.md)
* [ngx.shared.DICT.safe_set lance-2015.8.10](doc/ngxshareddictsafe_set.md)
* [ngx.shared.DICT.add lance-2015.8.10](doc/ngxshareddictadd.md)
* [ngx.shared.DICT.safe_add lance-2015.8.10](doc/ngxshareddictsafe_add.md)
* [ngx.shared.DICT.replace lance-2015.8.10](doc/ngxshareddictreplace.md)
* [ngx.shared.DICT.delete lance-2015.8.10](doc/ngxshareddictdelete.md)
* [ngx.shared.DICT.incr lance-2015.8.10](doc/ngxshareddictincr.md)
* [ngx.shared.DICT.flush_all lance-2015.8.10](doc/ngxshareddictflush_all.md)
* [ngx.shared.DICT.flush_expired lance-2015.8.10](doc/ngxshareddictflush_expired.md)
* [ngx.shared.DICT.get_keys lance-2015.8.10](doc/ngxshareddictget_keys.md)
* [ngx.socket.udp](#ngxsocketudp)
* [udpsock:setpeername](#udpsocksetpeername)
* [udpsock:send](#udpsocksend)
* [udpsock:receive](#udpsockreceive)
* [udpsock:close](#udpsockclose)
* [udpsock:settimeout](#udpsocksettimeout)
* [ngx.socket.tcp](#ngxsockettcp)
* [tcpsock:connect](#tcpsockconnect)
* [tcpsock:sslhandshake](#tcpsocksslhandshake)
* [tcpsock:send](#tcpsocksend)
* [tcpsock:receive](#tcpsockreceive)
* [tcpsock:receiveuntil](#tcpsockreceiveuntil)
* [tcpsock:close](#tcpsockclose)
* [tcpsock:settimeout](#tcpsocksettimeout)
* [tcpsock:setoption](#tcpsocksetoption)
* [tcpsock:setkeepalive](#tcpsocksetkeepalive)
* [tcpsock:getreusedtimes](#tcpsockgetreusedtimes)
* [ngx.socket.connect](#ngxsocketconnect)
* [ngx.get_phase](#ngxget_phase)
* [ngx.thread.spawn](#ngxthreadspawn)
* [ngx.thread.wait](#ngxthreadwait)
* [ngx.thread.kill](#ngxthreadkill)
* [ngx.on_abort](#ngxon_abort)
* [ngx.timer.at](#ngxtimerat)
* [ngx.config.debug](#ngxconfigdebug)
* [ngx.config.prefix](#ngxconfigprefix)
* [ngx.config.nginx_version](#ngxconfignginx_version)
* [ngx.config.nginx_configure](#ngxconfignginx_configure)
* [ngx.config.ngx_lua_version](#ngxconfigngx_lua_version)
* [ngx.worker.exiting](#ngxworkerexiting)
* [ngx.worker.pid](#ngxworkerpid)
* [ndk.set_var.DIRECTIVE](#ndkset_vardirective)
* [coroutine.create](#coroutinecreate)
* [coroutine.resume](#coroutineresume)
* [coroutine.yield](#coroutineyield)
* [coroutine.wrap](#coroutinewrap)
* [coroutine.running](#coroutinerunning)
* [coroutine.status](#coroutinestatus)
