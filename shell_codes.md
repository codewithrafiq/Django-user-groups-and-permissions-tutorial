```
(venv)
Administrator@XtremeLite-PC MINGW64 /f/Programming/Django-user-groups-and-permissions-tutorial (main)
$ python manage.py shell
Python 3.11.0 (main, Oct 24 2022, 18:26:48) [MSC v.1933 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
(InteractiveConsole)
>>> from django.contrib.auth.models import User,Permission,Group
>>> User.objects.all()
<QuerySet [<User: rafiq>]>
>>> user = User.objects.get(username="rafiq")
>>> user
<User: rafiq>
>>> user.id
1   
>>> user.username
'rafiq'
>>> user.email
'codewithrafiq@gmail.com'
>>> user.user_permissions.all()
<QuerySet []>
>>> user.user_permissions.all()
<QuerySet []>
>>>
>>> 
>>> 
>>> 
>>> 
>>> 
>>> 
>>> 
>>> 
>>> 
>>> 
>>> 
>>> 
>>> 
>>> 
>>> 
>>> 
>>> user.user_permissions.all()
<QuerySet []>
>>> Permission.objects.all()
<QuerySet [<Permission: admin | log entry | Can add log entry>, <Permission: admin | log entry | Can change log entry>, <Permission: admin | log entry | Can delete log entry>, 
<Permission: admin | log entry | Can view log entry>, <Permission: auth | group | Can add group>, <Permission: auth | group | Can change group>, <Permission: auth | group | Can delete group>, <Permission: auth | group | Can view group>, <Permission: auth | permission | Can add permission>, <Permission: auth | permission | Can change permission>, <Permission: auth | permission | Can delete permission>, <Permission: auth | permission | Can view permission>, <Permission: auth | user | Can add user>, <Permission: auth | user | Can change user>, <Permission: auth | user | Can delete user>, <Permission: auth | user | Can view user>, <Permission: contenttypes | content type | Can add content type>, <Permission: contenttypes | content type | Can change content type>, <Permission: contenttypes | content type | Can delete content type>, <Permission: contenttypes | content type 
| Can view content type>, '...(remaining elements truncated)...']>

>>> 
>>> 
>>> 
>>> 
>>> 
>>> 
>>> 
>>> 
>>> 
>>> 
>>> 
>>> 
>>> 
>>> 
>>> 
>>> 
>>> 
>>> for permission in Permission.objects.all():
...     print(permission)
... 
admin | log entry | Can add log entry
admin | log entry | Can change log entry
admin | log entry | Can delete log entry
admin | log entry | Can view log entry
auth | group | Can add group
auth | group | Can change group
auth | group | Can delete group
auth | group | Can view group
auth | permission | Can add permission
auth | permission | Can change permission
auth | permission | Can delete permission
auth | permission | Can view permission
auth | user | Can add user
auth | user | Can change user
auth | user | Can delete user
auth | user | Can view user
contenttypes | content type | Can add content type
contenttypes | content type | Can change content type
contenttypes | content type | Can delete content type
contenttypes | content type | Can view content type
sessions | session | Can add session
sessions | session | Can change session
sessions | session | Can delete session
sessions | session | Can view session
>>> Group.objects.all()
<QuerySet []>
>>> Group.__dict__        
mappingproxy({'__module__': 'django.contrib.auth.models', '__doc__': "\n    Groups are a generic way of categorizing users to apply permissions, or\n    some other label, to those users. A user can belong to any number of\n    groups.\n\n    A user in a group automatically has all the permissions granted to that\n    group. For example, if the group 
'Site editors' has the permission\n    can_edit_home_page, any user in that group will have that permission.\n\n    Beyond permissions, groups are a convenient way to categorize users to\n    apply some label, or extended functionality, to them. For example, you\n    could create a group 'Special users', and you could write code that would\n    do special things to those users -- such as giving them access to a\n    members-only portion of your site, or sending them members-only email\n    messages.\n    ", '__str__': <function Group.__str__ at 0x0000029C50A6D940>, 'natural_key': <function Group.natural_key at 0x0000029C5178D620>, '_meta': <Options for Group>, 'DoesNotExist': <class 'django.contrib.auth.models.Group.DoesNotExist'>, 'MultipleObjectsReturned': <class 'django.contrib.auth.models.Group.MultipleObjectsReturned'>, 'name': <django.db.models.query_utils.DeferredAttribute object at 0x0000029C51791950>, 'permissions': <django.db.models.fields.related_descriptors.ManyToManyDescriptor object at 0x0000029C51798E10>, 'objects': <django.db.models.manager.ManagerDescriptor object at 0x0000029C4FEEF090>, 'id': <django.db.models.query_utils.DeferredAttribute object at 0x0000029C51798F90>, 'user_set': <django.db.models.fields.related_descriptors.ManyToManyDescriptor object at 0x0000029C517A78D0>})    
>>> Group.objects.create(name="group1")
<Group: group1>
>>> group = Group.ojects.get(name="group1")
Traceback (most recent call last):
  File "<console>", line 1, in <module>
AttributeError: type object 'Group' has no attribute 'ojects'
>>> group = Group.objects.get(name="group1")
>>> group.id
1
>>> group.name
'group1'
>>> group.permissions
<django.db.models.fields.related_descriptors.create_forward_many_to_many_manager.<locals>.ManyRelatedManager object at 0x0000029C50578FD0>
>>>
>>> 
>>> 
>>> 
>>> 
>>> 
>>> 
>>> 
>>> 
>>> 
>>> 
>>> 
>>> 
>>> 
>>> 
>>> 
>>> 
>>> group.id
1
>>> group.name
'group1'
>>> group.permissions.all()
<QuerySet []>
>>> p1 = Permission.object.get(id=1)
Traceback (most recent call last):
  File "<console>", line 1, in <module>
AttributeError: type object 'Permission' has no attribute 'object'
>>> p1 = Permission.objects.get(id=1)
>>> p1
<Permission: admin | log entry | Can add log entry>
>>> p1.id
1
>>> p1.__dict__
{'_state': <django.db.models.base.ModelState object at 0x0000029C518322D0>, 'id': 1, 'name': 'Can add log entry', 'content_type_id': 1, 'codename': 'add_logentry'}
>>> group.permissons.add(p1) 
Traceback (most recent call last):
  File "<console>", line 1, in <module>
AttributeError: 'Group' object has no attribute 'permissons'
>>>
>>> 
>>> 
>>> 
>>> 
>>> 
>>> 
>>> 
>>> 
>>> 
>>> 
>>> 
>>> 
>>> 
>>> 
>>> 
>>> 
>>> p1 = Permission.objects.get(id=1)
>>> p1
<Permission: admin | log entry | Can add log entry>
>>> p1.__dict__
{'_state': <django.db.models.base.ModelState object at 0x0000029C518359D0>, 'id': 1, 'name': 'Can add log entry', 'content_type_id': 1, 'codename': 'add_logentry'}
>>> group.id
1
>>> group.permissions.add(p1) 
>>> group.permissions.all()
<QuerySet [<Permission: admin | log entry | Can add log entry>]>
>>> user.id
1
>>> user.usrname
Traceback (most recent call last):
  File "<console>", line 1, in <module>
AttributeError: 'User' object has no attribute 'usrname'
>>> user.username
'rafiq'
>>> user.group.add(group) 
Traceback (most recent call last):
  File "<console>", line 1, in <module>
AttributeError: 'User' object has no attribute 'group'
>>>
>>> 
>>> 
>>> 
>>> 
>>> 
>>> 
>>> 
>>> 
>>> 
>>> 
>>> 
>>> 
>>> 
>>> 
>>> 
>>> 
>>> user.username
'rafiq'
>>> user.id
1
>>> group.name
'group1'
>>> group.id
1
>>> user.groups.add(group) 
>>> user.groups.all()
<QuerySet [<Group: group1>]>
>>> Group.objects.create(name="group2") 
<Group: group2>
>>> p1
<Permission: admin | log entry | Can add log entry>
>>> p2 = Permission.objects.get(id=6)
>>> p2.id
6
>>> p2.name
'Can change permission'
>>> user.id
1
>>> user.user_permissions.all()
<QuerySet []>
>>> user.groups.all()
<QuerySet [<Group: group1>]>
>>> user.user_permissions.add(p2)
>>> user.user_permissions.all()
$ python manage.py shell



Python 3.11.0 (main, Oct 24 2022, 18:26:48) [MSC v.1933 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
(InteractiveConsole)
>>> from django.contrib.auth.models import Permission
>>> for permission in Permission.objects.all():
...     print(permission)
... 
admin | log entry | Can add log entry   
admin | log entry | Can change log entry
admin | log entry | Can delete log entry
admin | log entry | Can view log entry  
auth | group | Can add group
auth | group | Can change group
auth | group | Can delete group
auth | group | Can view group
auth | permission | Can add permission
auth | permission | Can change permission
auth | permission | Can delete permission
auth | permission | Can view permission
auth | user | Can add user
auth | user | Can change user
auth | user | Can delete user
auth | user | Can view user
contenttypes | content type | Can add content type
contenttypes | content type | Can change content type
contenttypes | content type | Can delete content type
contenttypes | content type | Can view content type
sessions | session | Can add session
sessions | session | Can change session
sessions | session | Can delete session
sessions | session | Can view session
todoapp | todo | Can add todo
todoapp | todo | Can change todo
todoapp | todo | Can delete todo
todoapp | todo | Can view todo
>>>






