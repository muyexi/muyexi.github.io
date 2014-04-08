---
layout: post
title: "AFNetworking parse JSON Unescaped control character"
date: 2014-04-08 21:07:16 +0800
comments: true
categories: iOS
---

 1.Add [chandan's method](http://stackoverflow.com/a/13741652/2122622) 

	removeUnescapedCharacter

 to class 

    AFURLResponseSerialization

 in AFNetworking 2.0.

 2.Add 

    responseString = [self removeUnescapedCharacter:responseString];

under 

    NSString *responseString = [[NSString alloc] initWithData:data encoding:stringEncoding];

in method

    - (id)responseObjectForResponse:(NSURLResponse *)response
                           data:(NSData *)data
                          error:(NSError *__autoreleasing *)error
