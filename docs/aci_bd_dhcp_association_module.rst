.. _aci_bd_dhcp_assocation:


aci_bd_dhcp_assocation - Manage DHCP Relay Labels in Bridge Domains (BD) on Cisco ACI fabrics (dhcp:Lbl)
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 2.4


.. contents::
   :local:
   :depth: 2


Synopsis
--------

* Manage DHCP Relay Labels in Bridge Domains (BD) on Cisco ACI fabrics.
* More information from the internal APIC class *dhcp:Lbl* at https://developer.cisco.com/media/mim-ref/MO-dhcpLbl.html.


Requirements (on host that executes module)
-------------------------------------------

  * ACI Fabric 1.0(3f)+


Options
-------

.. raw:: html

    <table border=1 cellpadding=4>

    <tr>
    <th class="head">parameter</th>
    <th class="head">required</th>
    <th class="head">default</th>
    <th class="head">choices</th>
    <th class="head">comments</th>
    </tr>

    <tr>
    <td>action<br/><div style="font-size: small;"></div></td>
    <td>yes</td>
    <td></td>
    <td><ul><li>post</li><li>get</li><li>delete</li></ul></td>
    <td>
        <div>post, get, and delete</div>
    </td>
    </tr>

    <tr>
    <td>bd_name<br/><div style="font-size: small;"></div></td>
    <td>yes</td>
    <td></td>
    <td></td>
    <td>
        <div>Bridge Domain</div>
    </td>
    </tr>

    <tr>
    <td>dhcp_name<br/><div style="font-size: small;"></div></td>
    <td>no</td>
    <td></td>
    <td></td>
    <td>
        <div>Name for the DHCP relay label to be added</div>
    </td>
    </tr>

    <tr>
    <td>dhcp_scope<br/><div style="font-size: small;"></div></td>
    <td>no</td>
    <td>infra</td>
    <td><ul><li>tenant</li><li>infra</li></ul></td>
    <td>
        <div>DHCP Relay label scope can be either tenant or infra</div>
    </td>
    </tr>

    <tr>
    <td>host<br/><div style="font-size: small;"></div></td>
    <td>yes</td>
    <td></td>
    <td></td>
    <td>
        <div>IP Address or hostname of APIC resolvable by Ansible control host</div>
    </td>
    </tr>

    <tr>
    <td>password<br/><div style="font-size: small;"></div></td>
    <td>yes</td>
    <td></td>
    <td></td>
    <td>
        <div>Password used to login to the switch</div>
    </td>
    </tr>

    <tr>
    <td>protocol<br/><div style="font-size: small;"></div></td>
    <td>no</td>
    <td>https</td>
    <td><ul><li>http</li><li>https</li></ul></td>
    <td>
        <div>Dictates connection protocol to use</div>
    </td>
    </tr>

    <tr>
    <td>tenant_name<br/><div style="font-size: small;"></div></td>
    <td>yes</td>
    <td></td>
    <td></td>
    <td>
        <div>Tenant Name</div>
    </td>
    </tr>

    <tr>
    <td>username<br/><div style="font-size: small;"></div></td>
    <td>yes</td>
    <td>admin</td>
    <td></td>
    <td>
        <div>Username used to login to the switch</div>
    </td>
    </tr>

    </table>
    </br>



Examples
--------

 ::

    
    - aci_bd_dhcp_association:
        action: "{{ action }}"
        tenant_name: "{{ tenant_name }}"
        bd_name: "{{ bd_name }}"
        dhcp_name: "{{ dhcp_name }}"
        dhcp_scope: "{{ dhcp_scope }}"
        host: "{{ inventory_hostname }}"
        username: "{{ username }}"
        password: "{{ password }}"
        protocol: "{{ protocol }}"


Notes
-----

.. note::
    - The ``tenant`` used must exist before using this module in your playbook. The :ref:`aci_tenant <aci_tenant>` module can be used for this.



Status
~~~~~~

This module is flagged as **preview** which means that it is not guaranteed to have a backwards compatible interface.

For help in developing on modules, should you be so inclined, please read :doc:`community`, :doc:`dev_guide/testing` and :doc:`dev_guide/developing_modules`.
