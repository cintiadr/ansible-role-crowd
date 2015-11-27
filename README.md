Ansible Role for Crowd
======================

[![Build Status](https://travis-ci.org/pantarei/ansible-role-crowd.svg?branch=master)](https://travis-ci.org/pantarei/ansible-role-crowd)
 [![GitHub tag](https://img.shields.io/github/tag/pantarei/ansible-role-crowd.svg)](https://github.com/pantarei/ansible-role-crowd)
 [![GitHub license](https://img.shields.io/github/license/pantarei/ansible-role-crowd.svg)](https://github.com/pantarei/ansible-role-crowd/blob/master/LICENSE)
 [![Ansible Role](https://img.shields.io/ansible/role/5987.svg)](https://galaxy.ansible.com/detail#/role/5987)

Ansible Role for Atlassian Crowd Installation.

Requirements
------------

This role require Ansible 1.9 or higher.

This role was designed for Ubuntu Server 14.04 LTS.

Role Variables
--------------

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">parameter</th>
<th align="left">required</th>
<th align="left">default</th>
<th align="left">choices</th>
<th align="left">comments</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">crowd_archive</td>
<td align="left">yes</td>
<td align="left"><a href="https://github.com/pantarei/ansible-role-crowd/blob/master/defaults/main.yml">defaults/main.yml</a></td>
<td align="left"></td>
<td align="left">Download archive filename for cache during (re)install.</td>
</tr>
<tr class="even">
<td align="left">crowd_catalina</td>
<td align="left">yes</td>
<td align="left">/usr/share/crowd</td>
<td align="left"></td>
<td align="left">Location for the Crowd installation directory.</td>
</tr>
<tr class="odd">
<td align="left">crowd_connector_port</td>
<td align="left">yes</td>
<td align="left">8095</td>
<td align="left"></td>
<td align="left">Crowd Apache Tomcat connector port.</td>
</tr>
<tr class="even">
<td align="left">crowd_home</td>
<td align="left">yes</td>
<td align="left">/var/lib/crowd</td>
<td align="left"></td>
<td align="left">Location for the Crowd home directory.</td>
</tr>
<tr class="odd">
<td align="left">crowd_jvm_maximum_memory</td>
<td align="left">yes</td>
<td align="left">1024m</td>
<td align="left"></td>
<td align="left">Crowd JVM maximum memory usage.</td>
</tr>
<tr class="even">
<td align="left">crowd_jvm_minimum_memory</td>
<td align="left">yes</td>
<td align="left">512m</td>
<td align="left"></td>
<td align="left">Crowd JVM minimum memory usage.</td>
</tr>
<tr class="odd">
<td align="left">crowd_jvm_support_recommended_args</td>
<td align="left">no</td>
<td align="left"><a href="https://github.com/pantarei/ansible-role-crowd/blob/master/defaults/main.yml">defaults/main.yml</a></td>
<td align="left"></td>
<td align="left">Atlassian Support recommended JVM arguments.</td>
</tr>
<tr class="even">
<td align="left">crowd_pass</td>
<td align="left">yes</td>
<td align="left">Wa6beegh</td>
<td align="left"></td>
<td align="left">Password for Crowd system user.</td>
</tr>
<tr class="odd">
<td align="left">crowd_proxy_name</td>
<td align="left">no</td>
<td align="left"><code>null</code></td>
<td align="left"></td>
<td align="left">Pass value as <code>proxyName</code> to <a href="https://github.com/pantarei/ansible-role-crowd/blob/master/templates/usr/share/crowd/conf/server.xml.j2">template</a>.</td>
</tr>
<tr class="even">
<td align="left">crowd_scheme</td>
<td align="left">no</td>
<td align="left"><code>null</code></td>
<td align="left"><ul>
<li><code>null</code></li>
<li>http</li>
<li>https</li>
</ul></td>
<td align="left">Install Crowd in standalone mode if <code>null</code>, or integrating with Apache using HTTP if <code>http</code>, or integrating with Apache using HTTPS if <code>https</code>.</td>
</tr>
<tr class="odd">
<td align="left">crowd_server_port</td>
<td align="left">yes</td>
<td align="left">8020</td>
<td align="left"></td>
<td align="left">Crowd Apache Tomcat server port.</td>
</tr>
<tr class="even">
<td align="left">crowd_sha256</td>
<td align="left">yes</td>
<td align="left"><a href="https://github.com/pantarei/ansible-role-crowd/blob/master/defaults/main.yml">defaults/main.yml</a></td>
<td align="left"></td>
<td align="left">Download archive sha256 checksum for cache during (re)install.</td>
</tr>
<tr class="odd">
<td align="left">crowd_upgrade</td>
<td align="left">no</td>
<td align="left"><code>false</code></td>
<td align="left"><ul>
<li><code>true</code></li>
<li><code>false</code></li>
</ul></td>
<td align="left">If <code>true</code>, trigger upgrade by stop existing Crowd service, purge existing Crowd installation direcoty before normal tasks.</td>
</tr>
<tr class="even">
<td align="left">crowd_url</td>
<td align="left">yes</td>
<td align="left"><a href="https://github.com/pantarei/ansible-role-crowd/blob/master/defaults/main.yml">defaults/main.yml</a></td>
<td align="left"></td>
<td align="left">URL for download archive.</td>
</tr>
<tr class="odd">
<td align="left">crowd_user</td>
<td align="left">yes</td>
<td align="left">crowd</td>
<td align="left"></td>
<td align="left">Username for Crowd system user.</td>
</tr>
</tbody>
</table>

Dependencies
------------

-   [hswong3i.java](https://github.com/pantarei/ansible-role-java)
-   [hswong3i.ufw](https://github.com/pantarei/ansible-role-ufw)

Example Playbook
----------------

    - hosts: servers
      roles:
        - { role: hswong3i.crowd, crowd_user: 'crowd', crowd_pass: 'Wa6beegh', crowd_upgrade: 'false' }

License
-------

-   Code released under [MIT](https://github.com/pantarei/ansible-role-crowd/blob/master/LICENSE)
-   Docs released under [CC BY 4.0](http://creativecommons.org/licenses/by/4.0/)

Author Information
------------------

-   Wong Hoi Sing Edison
    -   <https://twitter.com/hswong3i>
    -   <https://github.com/hswong3i>

