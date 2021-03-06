.. note::

  This repository has no longer maintained.

  Please use some forks, e.g. `lean-delivery/ansible-lint-rules <https://github.com/lean-delivery/ansible-lint-rules>`_


====================================
Rules for ansible-lint
====================================

This is a rule set for `ansible-lint <https://github.com/willthames/ansible-lint>`_ .

These rules are used in the `Tsukinowa Inc. <http://tsukinowa.jp>`_ , but anyone can use with the license (MIT).

How to use
----------------

1. Install `ansible-lint` (ex: `pip install ansible-lint`)
2. Copy or `git clone` on your ansible playbook repository with `rules` name
3. Run ansible lint with `-r rules` flag (ex: `ansible-lint -r rules <your playbook file>`)


Rules
=========

+------------+----------------------------------------------------------------------+
|code        |sample message                                                        |
+============+======================================================================+
|**E1**      |*playbook*                                                            |
+------------+----------------------------------------------------------------------+
|E101        |Playbook should has ".yml" extension                                  |
+------------+----------------------------------------------------------------------+
+------------+----------------------------------------------------------------------+
|**E2**      |*Role*                                                                |
+------------+----------------------------------------------------------------------+
|E201        |Doesn't need a relative path in role                                  |
+------------+----------------------------------------------------------------------+
+------------+----------------------------------------------------------------------+
|**E3**      |*Task*                                                                |
+------------+----------------------------------------------------------------------+
|E301        |All tasks should be named                                             |
+------------+----------------------------------------------------------------------+
|E302        |Include should has tags                                               |
+------------+----------------------------------------------------------------------+
|E303        |Use ":" YAML syntax when arguments are over 4                         |
+------------+----------------------------------------------------------------------+
|E304        |Do not use local_action. use delegate_to: localhost instead           |
+------------+----------------------------------------------------------------------+
|E305        |Variable should has space "{{ foo }}"                                 |
+------------+----------------------------------------------------------------------+
+------------+----------------------------------------------------------------------+
|**E4**      |*Module*                                                              |
+------------+----------------------------------------------------------------------+
|E401        |Octal file permissions must contain leading zero                      |
+------------+----------------------------------------------------------------------+
|E402        |Template file should has '.j2' extension                              |
+------------+----------------------------------------------------------------------+
+------------+----------------------------------------------------------------------+
|**E5**      |*Shell/Command alternative module*                                    |
+------------+----------------------------------------------------------------------+
|E501        |Use chmod module                                                      |
+------------+----------------------------------------------------------------------+
|E502        |Use chown module                                                      |
+------------+----------------------------------------------------------------------+
|E503        |Use hostname module                                                   |
+------------+----------------------------------------------------------------------+
|E504        |Use mount module                                                      |
+------------+----------------------------------------------------------------------+
|E505        |Use nmcli module                                                      |
+------------+----------------------------------------------------------------------+
|E506        |Use yum module with file path                                         |
+------------+----------------------------------------------------------------------+
|E507        |Use service module                                                    |
+------------+----------------------------------------------------------------------+
|E508        |Use sysctl module                                                     |
+------------+----------------------------------------------------------------------+
|E509        |Use ufw module                                                        |
+------------+----------------------------------------------------------------------+
|E510        |Use unarchive module                                                  |
+------------+----------------------------------------------------------------------+
|E511        |Shell/command module must contain creates or removes                  |
+------------+----------------------------------------------------------------------+
|E512        |Use file module instead of mkdir, ln -s and so on                     |
+------------+----------------------------------------------------------------------+
+------------+----------------------------------------------------------------------+
|**E6**      |*Formatting*                                                          |
+------------+----------------------------------------------------------------------+
|E601        |Trailing whitespace                                                   |
+------------+----------------------------------------------------------------------+
|E602        |Line too long                                                         |
+------------+----------------------------------------------------------------------+
+------------+----------------------------------------------------------------------+


Why so many shell module lint?
---------------------------------------------------------

Because user may want to use a command to correct use. Since we separete these rule, user can disable specific rule easily.

If you can manage playbook your self, consider set `skip_ansible_lint` tag.




License
==============

MIT License (same as ansible-lint)
