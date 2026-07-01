# Storage Units

The storage-unit mode makes the chest to be able to hold infinite amount of an item inside it. It has only one slot available, and it can hold only one item at a time without a limit to it.

{% hint style="warning" %}
Storage units can hold a lot of items. Once broken, all of these items will be dropped on ground. It's recommend to have a plugin that can stack items or a plugin that can limit items to avoid lag issues.
{% endhint %}

### Max Amount

You can limit the maximum amount of items a storage unit can hold. You can do that by setting the `max-amount` section with the maximum amount of items it can hold:

```yaml
chests:
  storage_unit:
    chest-mode: STORAGE_UNIT
    max-amount: 100000
```

{% hint style="info" %}
The storage unit will only be able to hold up to 100,000 items inside it.
{% endhint %}
