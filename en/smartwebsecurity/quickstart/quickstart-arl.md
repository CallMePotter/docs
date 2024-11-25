# Getting started with an ARL profile

{% include [briefly-about-arl](../../_includes/smartwebsecurity/briefly-about-arl.md) %}

Create your first [ARL profile](../concepts/arl.md) and connect it to an existing {{ sws-full-name }} [security profile](../concepts/profiles.md).

If you have not configured a security profile yet, create it and connect it to a [virtual host](../../application-load-balancer/concepts/http-router.md#virtual-host) of an {{ alb-full-name }} L7 load balancer. For more information, see [{#T}](../quickstart.md).

To get started with ARL:
1. [Create an ARL profile](#profile-create).
1. [Configure rules](#configure-rules).
1. [Connect your ARL profile to a security profile](#profile-connect).

## Prepare your cloud {#before-you-begin}

{% include [before-you-begin](../../_tutorials/_tutorials_includes/before-you-begin.md) %}

## Create an ARL profile {#profile-create}

{% list tabs group=instructions %}

- Management console {#console}

  1. In the [management console]({{ link-console-main }}), select the folder you want to create your ARL profile in.
  1. In the list of services, select **{{ ui-key.yacloud.iam.folder.dashboard.label_smartwebsecurity }}**.
  1. Go to the ![image](../../_assets/smartwebsecurity/arl.svg) **ARL profiles** tab and click **Create ARL profile**.
  1. Enter a name for the profile, e.g., `test-arl-profile-1`.
  1. Add profile description and labels if needed.
  1. Click **Create**.

{% endlist %}

## Configure rules {#configure-rules}

{% list tabs group=instructions %}

- Management console {#console}

  1. Click **Add a rule** on the ARL profile's review page that opens.
  1. Enter a name for the rule, e.g., `arl-rule-1`.
  1. In the **Priority** field, set the rule's priority within the ARL profile, e.g., `1000`.
  1. (Optional) To test the ARL rule, enable the **Logging only (Dry run)** mode. Requests will not be blocked in this mode.
  1. Under **Traffic conditions**, select **All traffic** or **With a condition**.
  1. To set [traffic conditions](../concepts/conditions.md), select one or more items from the **Conditions** list:
     *  `IP`: IP address, IP address range, or IP address region.
     *  `HTTP header`: HTTP header string.
     *  `HTTP body`: String in the HTTP packet body.
     *  `Request path`: Request path.
     *  `Host`: Domain receiving the request.
     *  `HTTP method`: Request method.
     *  `Cookie`: Cookie header string.
  
  1. Under **Request counting**, select how to count requests for limit application purposes:
     * **No grouping**: Counting each request individually.
     * **Grouping by property**: Counting the number of request groups sharing one or multiple common properties.
        1. Select a grouping property:
            *  `Request path`: Request path.
            *  `HTTP method`: Request method.
            *  `IP address`: IP address the request came from.
            *  `Region`: IP address region of the requests.
            *  `Host`: Domain receiving the request.
            *  `HTTP cookie`: String in the cookie header.
            *  `HTTP header`: HTTP header string.
            *  `Query params`: String in query parameters.
        1. (Optional) Enable **Case-sensitive** to put properties with the same values in different cases into different groups.

  1. Specify the request limit and select the time interval, e.g., `1000` requests per `1` minute.

  1. Click **Save rule**.

{% endlist %}

## Connect your ARL profile to a security profile {#profile-connect}

{% list tabs group=instructions %}

- Management console {#console}

  1. Go to the ![image](../../_assets/console-icons/shield-check.svg) **{{ ui-key.yacloud.smart-web-security.title_profiles }}** tab.
  1. From the list, select the security profile you want to connect your ARL profile to, e.g., `test-sp1`.
  1. Click **Edit**.
  1. From the **ARL profile** list, select `test-arl-profile-1` you created earlier.
  1. Click **Save**.

{% endlist %}

### See also {#see-also}

* [{#T}](../quickstart.md)
* [{#T}](../concepts/arl.md)
