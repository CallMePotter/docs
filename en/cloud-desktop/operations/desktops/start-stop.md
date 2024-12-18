---
title: How to launch, restart, and stop a desktop in {{ cloud-desktop-full-name }}
description: In this tutorial, you will learn how to launch, restart, and stop a desktop in {{ cloud-desktop-name }}.
---

# Launching, restarting, and stopping a desktop

## Start {#start}

{% list tabs group=instructions %}

- Management console {#console}

  1. In the [management console]({{ link-console-main }}), select the folder containing the desktop.
  1. In the list of services, select **{{ ui-key.yacloud.iam.folder.dashboard.label_cloud-desktop }}**.
  1. In the left-hand panel, select ![image](../../../_assets/console-icons/display.svg) **{{ ui-key.yacloud.vdi.label_desktops }}**.
  1. Next to the desktop to launch, click ![options](../../../_assets/console-icons/ellipsis.svg) and select **{{ ui-key.yacloud.vdi.button_start }}**.
  1. Confirm that you want to launch the desktop.

- User desktop showcase {#desktop-showcase}

  1. Open the [User desktop showcase]({{ link-cloud-desktop-showcase }}).
  1. In the card of the desktop to launch, click ![image](../../../_assets/console-icons/play.svg).
  1. Confirm that you want to launch the desktop.

{% endlist %}

## Restart {#restart}

{% list tabs group=instructions %}

- Management console {#console}

  1. In the [management console]({{ link-console-main }}), select the folder containing the desktop.
  1. In the list of services, select **{{ ui-key.yacloud.iam.folder.dashboard.label_cloud-desktop }}**.
  1. In the left-hand panel, select ![image](../../../_assets/console-icons/display.svg) **{{ ui-key.yacloud.vdi.label_desktops }}**.
  1. Next to the desktop to launch, click ![options](../../../_assets/console-icons/ellipsis.svg) and select **{{ ui-key.yacloud.vdi.button_restart }}**.
  1. Confirm that you want to restart the desktop.

- User desktop showcase {#desktop-showcase}

  1. Open the [User desktop showcase]({{ link-cloud-desktop-showcase }}).
  1. In the card of the desktop to restart, click ![image](../../../_assets/console-icons/arrow-rotate-right.svg).
  1. Confirm that you want to restart the desktop.

- {{ yandex-cloud }} CLI {#cli}

  {% include [cli-install](../../../_includes/cli-install.md) %}

  {% include [default-catalogue](../../../_includes/default-catalogue.md) %}

  1. View a description of the [CLI](../../../cli/index.yaml) command that restarts a [desktop](../../../cloud-desktop/concepts/desktops-and-groups.md):

      ```bash
      yc desktops desktop restart --help
      ```

  1. Get a list of desktops in the default folder:

      ```bash
      yc desktops desktop list
      ```

      Result:

      ```bash
      +----------------------+------------------+--------+----------------------+---------------------+
      |          ID          |       NAME       | STATUS |   DESKTOP GROUP ID   |   CREATED (UTC-0)   |
      +----------------------+------------------+--------+----------------------+---------------------+
      | e3vmvhgbgac4******** | my-cloud-desktop | ACTIVE | e3v1rbln45tl******** | 2024-10-09 22:42:28 |
      | e3vio1bc5ppz******** | reserved-desktop | ACTIVE | e3v1rbln45tl******** | 2024-10-09 21:35:17 |
      +----------------------+------------------+--------+----------------------+---------------------+
      ```

  1. Select the desktop `ID` or `NAME`, e.g., `my-cloud-desktop`.
  1. Restart the desktop:

      ```bash
      yc desktops desktop restart --name <desktop_name>
      ```

      {% include [create-desktop-cli-result](../../../_includes/cloud-desktop/create-desktop-cli-result.md) %}

{% endlist %}

## Stop {#stop}

{% list tabs group=instructions %}

- Management console {#console}

  1. In the [management console]({{ link-console-main }}), select the folder containing the desktop.
  1. In the list of services, select **{{ ui-key.yacloud.iam.folder.dashboard.label_cloud-desktop }}**.
  1. In the left-hand panel, select ![image](../../../_assets/console-icons/display.svg) **{{ ui-key.yacloud.vdi.label_desktops }}**.
  1. Next to the desktop to stop, click ![options](../../../_assets/console-icons/ellipsis.svg) and select **{{ ui-key.yacloud.vdi.button_stop }}**.
  1. Confirm that you want to stop the desktop.

- User desktop showcase {#desktop-showcase}

  1. Open the [User desktop showcase]({{ link-cloud-desktop-showcase }}).
  1. In the card of the desktop to stop, click ![image](../../../_assets/console-icons/power.svg).
  1. Confirm that you want to stop the desktop.

{% endlist %}
