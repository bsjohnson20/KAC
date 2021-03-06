# CBlob@ class
Blob class is used for pretty much everything. Its one of the core parts of KAG. Anything from players characters, spawn points like tents, boats and much more are a blob.

---

## void Init()
This calls all current scripts attached to the blob ``onInit(CBlob@ this)`` hook.
<br>
Called automatically when using ``server_CreateBlob(const string&in, int team, Vec2f Position)``
<br>
Can be called manually after using ``server_CreateBlobNoInit(const string&in)``, so attributes can be set before onInit is called
<br>
<br>
<small>Returns: void</small>

<details>
<summary>Example</summary>

```as
CBlob@ new_blob = server_CreateBlobNoInit("new_blob"); // new blob
if (new_blob !is null)
{
    new_blob.Tag("very-cool-tag"); // set some important tag/info
    new_blob.Init(); // tell the blob to Init all scripts
}
```

</details>
<br>
<br>

## float getHealth()
This returns an f32 in the amount of HP the blob currently has.
<br>
<br>
<small>Returns: f32 - current health (amount of hearts / 2)</small>

<details>
<summary>Example</summary>

```as
f32 currentHp = this.getHealth(); // lets say we have 2 hearts
print(currentHp+''); // this would print '1.0'
```

</details>
<br>
<br>

## float getInitialHealth()
This returns an f32 with the amount of HP stated in our blobs .cfg file.
<br>
<br>
<small>Returns: f32 - with starting hp (hearts / 2)</small>

<details>
<summary>Example</summary>

```as
f32 hpOnStart = this.getInitialHealth(); // lets say we started off with 3 hearts
print(hpOnStart+''); // this would print '1.5'
```

</details>
<br>
<br>
