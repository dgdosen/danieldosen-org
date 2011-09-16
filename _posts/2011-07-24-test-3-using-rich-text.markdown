--- 
layout: post
title: Test 3 using Rich Text...
tags: []

status: trash
type: post
published: false
meta: 
  _syntaxhighlighter_encoded: "1"
  _wp_trash_meta_status: publish
  _wp_trash_meta_time: "1311533701"
---
<p>Here's a post using rich text.</p>
<p><span style="font-family: monospace; white-space: pre;">[sourcecode language="ruby"]&amp;lt;/span&amp;gt;&amp;lt;/p&amp;gt;
&amp;lt;p&amp;gt;describe &amp;quot;POST create&amp;quot; do    # test code roundtripping with marsedit    it &amp;quot;should create a pomodoro from json&amp;quot; do      post :create, :format =&amp;amp;gt; &amp;quot;json&amp;quot;, :activity_id =&amp;amp;gt; @activity.id, :pomodoro =&amp;amp;gt; {        &amp;quot;start_date_time&amp;quot; =&amp;amp;gt; &amp;quot;2011-07-22 00:00&amp;quot;,        &amp;quot;length&amp;quot; =&amp;amp;gt; &amp;quot;25&amp;quot;,        &amp;quot;completed&amp;quot; =&amp;amp;gt; &amp;quot;0&amp;quot;,        &amp;quot;note&amp;quot; =&amp;amp;gt; &amp;quot;json post individual pomodoro&amp;quot;,        &amp;quot;break_length&amp;quot; =&amp;amp;gt; &amp;quot;5&amp;quot;      }      pomodoro = assigns(:pomodoro)      pomodoro.id.should &amp;amp;gt; 0      pomodoro.note.should == &amp;quot;json post individual pomodoro&amp;quot;      pomodoro.length.should == 25    end  end&amp;lt;/p&amp;gt;
&amp;lt;p&amp;gt;&amp;lt;span style=&amp;quot;font-family: monospace; white-space: pre;&amp;quot;&amp;gt;[/sourcecode]</span></p>
