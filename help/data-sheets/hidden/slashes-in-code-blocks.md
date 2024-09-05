---
title: Slashes in code blocks UGP-11189
description: Slashes in code blocks UGP-11189 test
hide: true
hidefromtoc: true
exl-id: d585d672-b617-4aba-83ac-1295ce8a55cb
---
# Slash in code blocks

1. Run the command:

    ```bash
    vendor/bin/magento-patches -n status |grep "27015\|Status"
    ```

1. Next step

Not in code block

vendor/bin/magento-patches -n status |grep "27015\|Status"

Escaped backslash:

vendor/bin/magento-patches -n status |grep "27015&bsol;|Status"
