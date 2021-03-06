---
title: Module loganalytics
title_tag: Module loganalytics | Package pulumi_azure | Python SDK
linktitle: loganalytics
notitle: true
block_external_search_index: true
---

{{< resource-docs-alert "azure" >}}

<div class="section" id="loganalytics">
<h1>loganalytics<a class="headerlink" href="#loganalytics" title="Permalink to this headline">¶</a></h1>
<blockquote>
<div><p>This provider is a derived work of the <a class="reference external" href="https://github.com/terraform-providers/terraform-provider-azurerm">Terraform Provider</a> distributed under
<a class="reference external" href="https://www.mozilla.org/en-US/MPL/2.0/">MPL 2.0</a>. If you encounter a bug or missing feature, first check the
<a class="reference external" href="https://github.com/pulumi/pulumi-azure/issues">pulumi/pulumi-azure repo</a>; however, if that doesn’t turn up
anything, please consult the source <a class="reference external" href="https://github.com/terraform-providers/terraform-provider-azurerm/issues">terraform-providers/terraform-provider-azurerm repo</a>.</p>
</div></blockquote>
<span class="target" id="module-pulumi_azure.loganalytics"></span><dl class="py class">
<dt id="pulumi_azure.loganalytics.DataSourceWindowsEvent">
<em class="property">class </em><code class="sig-prename descclassname">pulumi_azure.loganalytics.</code><code class="sig-name descname">DataSourceWindowsEvent</code><span class="sig-paren">(</span><em class="sig-param"><span class="n">resource_name</span></em>, <em class="sig-param"><span class="n">opts</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">event_log_name</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">event_types</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">name</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">resource_group_name</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">workspace_name</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">__props__</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">__name__</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">__opts__</span><span class="o">=</span><span class="default_value">None</span></em><span class="sig-paren">)</span><a class="headerlink" href="#pulumi_azure.loganalytics.DataSourceWindowsEvent" title="Permalink to this definition">¶</a></dt>
<dd><p>Manages a Log Analytics Windows Event DataSource.</p>
<div class="highlight-python notranslate"><div class="highlight"><pre><span></span><span class="kn">import</span> <span class="nn">pulumi</span>
<span class="kn">import</span> <span class="nn">pulumi_azure</span> <span class="k">as</span> <span class="nn">azure</span>

<span class="n">example_resource_group</span> <span class="o">=</span> <span class="n">azure</span><span class="o">.</span><span class="n">core</span><span class="o">.</span><span class="n">ResourceGroup</span><span class="p">(</span><span class="s2">&quot;exampleResourceGroup&quot;</span><span class="p">,</span> <span class="n">location</span><span class="o">=</span><span class="s2">&quot;West Europe&quot;</span><span class="p">)</span>
<span class="n">example_analytics_workspace</span> <span class="o">=</span> <span class="n">azure</span><span class="o">.</span><span class="n">operationalinsights</span><span class="o">.</span><span class="n">AnalyticsWorkspace</span><span class="p">(</span><span class="s2">&quot;exampleAnalyticsWorkspace&quot;</span><span class="p">,</span>
    <span class="n">location</span><span class="o">=</span><span class="n">example_resource_group</span><span class="o">.</span><span class="n">location</span><span class="p">,</span>
    <span class="n">resource_group_name</span><span class="o">=</span><span class="n">example_resource_group</span><span class="o">.</span><span class="n">name</span><span class="p">,</span>
    <span class="n">sku</span><span class="o">=</span><span class="s2">&quot;PerGB2018&quot;</span><span class="p">)</span>
<span class="n">example_data_source_windows_event</span> <span class="o">=</span> <span class="n">azure</span><span class="o">.</span><span class="n">loganalytics</span><span class="o">.</span><span class="n">DataSourceWindowsEvent</span><span class="p">(</span><span class="s2">&quot;exampleDataSourceWindowsEvent&quot;</span><span class="p">,</span>
    <span class="n">resource_group_name</span><span class="o">=</span><span class="n">example_resource_group</span><span class="o">.</span><span class="n">name</span><span class="p">,</span>
    <span class="n">workspace_name</span><span class="o">=</span><span class="n">example_analytics_workspace</span><span class="o">.</span><span class="n">name</span><span class="p">,</span>
    <span class="n">event_log_name</span><span class="o">=</span><span class="s2">&quot;Application&quot;</span><span class="p">,</span>
    <span class="n">event_types</span><span class="o">=</span><span class="p">[</span><span class="s2">&quot;error&quot;</span><span class="p">])</span>
</pre></div>
</div>
<dl class="field-list simple">
<dt class="field-odd">Parameters</dt>
<dd class="field-odd"><ul class="simple">
<li><p><strong>resource_name</strong> (<em>str</em>) – The name of the resource.</p></li>
<li><p><strong>opts</strong> (<a class="reference internal" href="../../pulumi/#pulumi.ResourceOptions" title="pulumi.ResourceOptions"><em>pulumi.ResourceOptions</em></a>) – Options for the resource.</p></li>
<li><p><strong>event_log_name</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – Specifies the name of the Windows Event Log to collect events from.</p></li>
<li><p><strong>event_types</strong> (<em>pulumi.Input</em><em>[</em><em>list</em><em>]</em>) – Specifies an array of event types applied to the specified event log. Possible values include <code class="docutils literal notranslate"><span class="pre">error</span></code>, <code class="docutils literal notranslate"><span class="pre">warning</span></code> and <code class="docutils literal notranslate"><span class="pre">information</span></code>.</p></li>
<li><p><strong>name</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – The name which should be used for this Log Analytics Windows Event DataSource. Changing this forces a new Log Analytics Windows Event DataSource to be created.</p></li>
<li><p><strong>resource_group_name</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – The name of the Resource Group where the Log Analytics Windows Event DataSource should exist. Changing this forces a new Log Analytics Windows Event DataSource to be created.</p></li>
<li><p><strong>workspace_name</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – The name of the Log Analytics Workspace where the Log Analytics Windows Event DataSource should exist. Changing this forces a new Log Analytics Windows Event DataSource to be created.</p></li>
</ul>
</dd>
</dl>
<dl class="py attribute">
<dt id="pulumi_azure.loganalytics.DataSourceWindowsEvent.event_log_name">
<code class="sig-name descname">event_log_name</code><em class="property">: pulumi.Output[str]</em><em class="property"> = None</em><a class="headerlink" href="#pulumi_azure.loganalytics.DataSourceWindowsEvent.event_log_name" title="Permalink to this definition">¶</a></dt>
<dd><p>Specifies the name of the Windows Event Log to collect events from.</p>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_azure.loganalytics.DataSourceWindowsEvent.event_types">
<code class="sig-name descname">event_types</code><em class="property">: pulumi.Output[list]</em><em class="property"> = None</em><a class="headerlink" href="#pulumi_azure.loganalytics.DataSourceWindowsEvent.event_types" title="Permalink to this definition">¶</a></dt>
<dd><p>Specifies an array of event types applied to the specified event log. Possible values include <code class="docutils literal notranslate"><span class="pre">error</span></code>, <code class="docutils literal notranslate"><span class="pre">warning</span></code> and <code class="docutils literal notranslate"><span class="pre">information</span></code>.</p>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_azure.loganalytics.DataSourceWindowsEvent.name">
<code class="sig-name descname">name</code><em class="property">: pulumi.Output[str]</em><em class="property"> = None</em><a class="headerlink" href="#pulumi_azure.loganalytics.DataSourceWindowsEvent.name" title="Permalink to this definition">¶</a></dt>
<dd><p>The name which should be used for this Log Analytics Windows Event DataSource. Changing this forces a new Log Analytics Windows Event DataSource to be created.</p>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_azure.loganalytics.DataSourceWindowsEvent.resource_group_name">
<code class="sig-name descname">resource_group_name</code><em class="property">: pulumi.Output[str]</em><em class="property"> = None</em><a class="headerlink" href="#pulumi_azure.loganalytics.DataSourceWindowsEvent.resource_group_name" title="Permalink to this definition">¶</a></dt>
<dd><p>The name of the Resource Group where the Log Analytics Windows Event DataSource should exist. Changing this forces a new Log Analytics Windows Event DataSource to be created.</p>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_azure.loganalytics.DataSourceWindowsEvent.workspace_name">
<code class="sig-name descname">workspace_name</code><em class="property">: pulumi.Output[str]</em><em class="property"> = None</em><a class="headerlink" href="#pulumi_azure.loganalytics.DataSourceWindowsEvent.workspace_name" title="Permalink to this definition">¶</a></dt>
<dd><p>The name of the Log Analytics Workspace where the Log Analytics Windows Event DataSource should exist. Changing this forces a new Log Analytics Windows Event DataSource to be created.</p>
</dd></dl>

<dl class="py method">
<dt id="pulumi_azure.loganalytics.DataSourceWindowsEvent.get">
<em class="property">static </em><code class="sig-name descname">get</code><span class="sig-paren">(</span><em class="sig-param"><span class="n">resource_name</span></em>, <em class="sig-param"><span class="n">id</span></em>, <em class="sig-param"><span class="n">opts</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">event_log_name</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">event_types</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">name</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">resource_group_name</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">workspace_name</span><span class="o">=</span><span class="default_value">None</span></em><span class="sig-paren">)</span><a class="headerlink" href="#pulumi_azure.loganalytics.DataSourceWindowsEvent.get" title="Permalink to this definition">¶</a></dt>
<dd><p>Get an existing DataSourceWindowsEvent resource’s state with the given name, id, and optional extra
properties used to qualify the lookup.</p>
<dl class="field-list simple">
<dt class="field-odd">Parameters</dt>
<dd class="field-odd"><ul class="simple">
<li><p><strong>resource_name</strong> (<em>str</em>) – The unique name of the resulting resource.</p></li>
<li><p><strong>id</strong> (<em>str</em>) – The unique provider ID of the resource to lookup.</p></li>
<li><p><strong>opts</strong> (<a class="reference internal" href="../../pulumi/#pulumi.ResourceOptions" title="pulumi.ResourceOptions"><em>pulumi.ResourceOptions</em></a>) – Options for the resource.</p></li>
<li><p><strong>event_log_name</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – Specifies the name of the Windows Event Log to collect events from.</p></li>
<li><p><strong>event_types</strong> (<em>pulumi.Input</em><em>[</em><em>list</em><em>]</em>) – Specifies an array of event types applied to the specified event log. Possible values include <code class="docutils literal notranslate"><span class="pre">error</span></code>, <code class="docutils literal notranslate"><span class="pre">warning</span></code> and <code class="docutils literal notranslate"><span class="pre">information</span></code>.</p></li>
<li><p><strong>name</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – The name which should be used for this Log Analytics Windows Event DataSource. Changing this forces a new Log Analytics Windows Event DataSource to be created.</p></li>
<li><p><strong>resource_group_name</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – The name of the Resource Group where the Log Analytics Windows Event DataSource should exist. Changing this forces a new Log Analytics Windows Event DataSource to be created.</p></li>
<li><p><strong>workspace_name</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – The name of the Log Analytics Workspace where the Log Analytics Windows Event DataSource should exist. Changing this forces a new Log Analytics Windows Event DataSource to be created.</p></li>
</ul>
</dd>
</dl>
</dd></dl>

<dl class="py method">
<dt id="pulumi_azure.loganalytics.DataSourceWindowsEvent.translate_output_property">
<code class="sig-name descname">translate_output_property</code><span class="sig-paren">(</span><em class="sig-param"><span class="n">prop</span></em><span class="sig-paren">)</span><a class="headerlink" href="#pulumi_azure.loganalytics.DataSourceWindowsEvent.translate_output_property" title="Permalink to this definition">¶</a></dt>
<dd><p>Provides subclasses of Resource an opportunity to translate names of output properties
into a format of their choosing before writing those properties to the resource object.</p>
<dl class="field-list simple">
<dt class="field-odd">Parameters</dt>
<dd class="field-odd"><p><strong>prop</strong> (<em>str</em>) – A property name.</p>
</dd>
<dt class="field-even">Returns</dt>
<dd class="field-even"><p>A potentially transformed property name.</p>
</dd>
<dt class="field-odd">Return type</dt>
<dd class="field-odd"><p>str</p>
</dd>
</dl>
</dd></dl>

<dl class="py method">
<dt id="pulumi_azure.loganalytics.DataSourceWindowsEvent.translate_input_property">
<code class="sig-name descname">translate_input_property</code><span class="sig-paren">(</span><em class="sig-param"><span class="n">prop</span></em><span class="sig-paren">)</span><a class="headerlink" href="#pulumi_azure.loganalytics.DataSourceWindowsEvent.translate_input_property" title="Permalink to this definition">¶</a></dt>
<dd><p>Provides subclasses of Resource an opportunity to translate names of input properties into
a format of their choosing before sending those properties to the Pulumi engine.</p>
<dl class="field-list simple">
<dt class="field-odd">Parameters</dt>
<dd class="field-odd"><p><strong>prop</strong> (<em>str</em>) – A property name.</p>
</dd>
<dt class="field-even">Returns</dt>
<dd class="field-even"><p>A potentially transformed property name.</p>
</dd>
<dt class="field-odd">Return type</dt>
<dd class="field-odd"><p>str</p>
</dd>
</dl>
</dd></dl>

</dd></dl>

<dl class="py class">
<dt id="pulumi_azure.loganalytics.DataSourceWindowsPerformanceCounter">
<em class="property">class </em><code class="sig-prename descclassname">pulumi_azure.loganalytics.</code><code class="sig-name descname">DataSourceWindowsPerformanceCounter</code><span class="sig-paren">(</span><em class="sig-param"><span class="n">resource_name</span></em>, <em class="sig-param"><span class="n">opts</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">counter_name</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">instance_name</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">interval_seconds</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">name</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">object_name</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">resource_group_name</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">workspace_name</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">__props__</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">__name__</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">__opts__</span><span class="o">=</span><span class="default_value">None</span></em><span class="sig-paren">)</span><a class="headerlink" href="#pulumi_azure.loganalytics.DataSourceWindowsPerformanceCounter" title="Permalink to this definition">¶</a></dt>
<dd><p>Manages a Log Analytics (formally Operational Insights) Windows Performance Counter DataSource.</p>
<div class="highlight-python notranslate"><div class="highlight"><pre><span></span><span class="kn">import</span> <span class="nn">pulumi</span>
<span class="kn">import</span> <span class="nn">pulumi_azure</span> <span class="k">as</span> <span class="nn">azure</span>

<span class="n">example_resource_group</span> <span class="o">=</span> <span class="n">azure</span><span class="o">.</span><span class="n">core</span><span class="o">.</span><span class="n">ResourceGroup</span><span class="p">(</span><span class="s2">&quot;exampleResourceGroup&quot;</span><span class="p">,</span> <span class="n">location</span><span class="o">=</span><span class="s2">&quot;West Europe&quot;</span><span class="p">)</span>
<span class="n">example_analytics_workspace</span> <span class="o">=</span> <span class="n">azure</span><span class="o">.</span><span class="n">operationalinsights</span><span class="o">.</span><span class="n">AnalyticsWorkspace</span><span class="p">(</span><span class="s2">&quot;exampleAnalyticsWorkspace&quot;</span><span class="p">,</span>
    <span class="n">location</span><span class="o">=</span><span class="n">example_resource_group</span><span class="o">.</span><span class="n">location</span><span class="p">,</span>
    <span class="n">resource_group_name</span><span class="o">=</span><span class="n">example_resource_group</span><span class="o">.</span><span class="n">name</span><span class="p">,</span>
    <span class="n">sku</span><span class="o">=</span><span class="s2">&quot;PerGB2018&quot;</span><span class="p">)</span>
<span class="n">example_data_source_windows_performance_counter</span> <span class="o">=</span> <span class="n">azure</span><span class="o">.</span><span class="n">loganalytics</span><span class="o">.</span><span class="n">DataSourceWindowsPerformanceCounter</span><span class="p">(</span><span class="s2">&quot;exampleDataSourceWindowsPerformanceCounter&quot;</span><span class="p">,</span>
    <span class="n">resource_group_name</span><span class="o">=</span><span class="n">example_resource_group</span><span class="o">.</span><span class="n">name</span><span class="p">,</span>
    <span class="n">workspace_name</span><span class="o">=</span><span class="n">example_analytics_workspace</span><span class="o">.</span><span class="n">name</span><span class="p">,</span>
    <span class="n">object_name</span><span class="o">=</span><span class="s2">&quot;CPU&quot;</span><span class="p">,</span>
    <span class="n">instance_name</span><span class="o">=</span><span class="s2">&quot;*&quot;</span><span class="p">,</span>
    <span class="n">counter_name</span><span class="o">=</span><span class="s2">&quot;CPU&quot;</span><span class="p">,</span>
    <span class="n">interval_seconds</span><span class="o">=</span><span class="mi">10</span><span class="p">)</span>
</pre></div>
</div>
<dl class="field-list simple">
<dt class="field-odd">Parameters</dt>
<dd class="field-odd"><ul class="simple">
<li><p><strong>resource_name</strong> (<em>str</em>) – The name of the resource.</p></li>
<li><p><strong>opts</strong> (<a class="reference internal" href="../../pulumi/#pulumi.ResourceOptions" title="pulumi.ResourceOptions"><em>pulumi.ResourceOptions</em></a>) – Options for the resource.</p></li>
<li><p><strong>counter_name</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – The friendly name of the performance counter.</p></li>
<li><p><strong>instance_name</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – The name of the virtual machine instance to which the Windows Performance Counter DataSource be applied. Specify a <code class="docutils literal notranslate"><span class="pre">*</span></code> will apply to all instances.</p></li>
<li><p><strong>interval_seconds</strong> (<em>pulumi.Input</em><em>[</em><em>float</em><em>]</em>) – The time of sample interval in seconds. Supports values between 10 and 2147483647.</p></li>
<li><p><strong>name</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – The Name which should be used for this Log Analytics Windows Performance Counter DataSource. Changing this forces a new Log Analytics Windows Performance Counter DataSource to be created.</p></li>
<li><p><strong>object_name</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – The object name of the Log Analytics Windows Performance Counter DataSource.</p></li>
<li><p><strong>resource_group_name</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – The name of the Resource Group where the Log Analytics Windows Performance Counter DataSource should exist. Changing this forces a new Log Analytics Windows Performance Counter DataSource to be created.</p></li>
<li><p><strong>workspace_name</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – The name of the Log Analytics Workspace where the Log Analytics Windows Performance Counter DataSource should exist. Changing this forces a new Log Analytics Windows Performance Counter DataSource to be created.</p></li>
</ul>
</dd>
</dl>
<dl class="py attribute">
<dt id="pulumi_azure.loganalytics.DataSourceWindowsPerformanceCounter.counter_name">
<code class="sig-name descname">counter_name</code><em class="property">: pulumi.Output[str]</em><em class="property"> = None</em><a class="headerlink" href="#pulumi_azure.loganalytics.DataSourceWindowsPerformanceCounter.counter_name" title="Permalink to this definition">¶</a></dt>
<dd><p>The friendly name of the performance counter.</p>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_azure.loganalytics.DataSourceWindowsPerformanceCounter.instance_name">
<code class="sig-name descname">instance_name</code><em class="property">: pulumi.Output[str]</em><em class="property"> = None</em><a class="headerlink" href="#pulumi_azure.loganalytics.DataSourceWindowsPerformanceCounter.instance_name" title="Permalink to this definition">¶</a></dt>
<dd><p>The name of the virtual machine instance to which the Windows Performance Counter DataSource be applied. Specify a <code class="docutils literal notranslate"><span class="pre">*</span></code> will apply to all instances.</p>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_azure.loganalytics.DataSourceWindowsPerformanceCounter.interval_seconds">
<code class="sig-name descname">interval_seconds</code><em class="property">: pulumi.Output[float]</em><em class="property"> = None</em><a class="headerlink" href="#pulumi_azure.loganalytics.DataSourceWindowsPerformanceCounter.interval_seconds" title="Permalink to this definition">¶</a></dt>
<dd><p>The time of sample interval in seconds. Supports values between 10 and 2147483647.</p>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_azure.loganalytics.DataSourceWindowsPerformanceCounter.name">
<code class="sig-name descname">name</code><em class="property">: pulumi.Output[str]</em><em class="property"> = None</em><a class="headerlink" href="#pulumi_azure.loganalytics.DataSourceWindowsPerformanceCounter.name" title="Permalink to this definition">¶</a></dt>
<dd><p>The Name which should be used for this Log Analytics Windows Performance Counter DataSource. Changing this forces a new Log Analytics Windows Performance Counter DataSource to be created.</p>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_azure.loganalytics.DataSourceWindowsPerformanceCounter.object_name">
<code class="sig-name descname">object_name</code><em class="property">: pulumi.Output[str]</em><em class="property"> = None</em><a class="headerlink" href="#pulumi_azure.loganalytics.DataSourceWindowsPerformanceCounter.object_name" title="Permalink to this definition">¶</a></dt>
<dd><p>The object name of the Log Analytics Windows Performance Counter DataSource.</p>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_azure.loganalytics.DataSourceWindowsPerformanceCounter.resource_group_name">
<code class="sig-name descname">resource_group_name</code><em class="property">: pulumi.Output[str]</em><em class="property"> = None</em><a class="headerlink" href="#pulumi_azure.loganalytics.DataSourceWindowsPerformanceCounter.resource_group_name" title="Permalink to this definition">¶</a></dt>
<dd><p>The name of the Resource Group where the Log Analytics Windows Performance Counter DataSource should exist. Changing this forces a new Log Analytics Windows Performance Counter DataSource to be created.</p>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_azure.loganalytics.DataSourceWindowsPerformanceCounter.workspace_name">
<code class="sig-name descname">workspace_name</code><em class="property">: pulumi.Output[str]</em><em class="property"> = None</em><a class="headerlink" href="#pulumi_azure.loganalytics.DataSourceWindowsPerformanceCounter.workspace_name" title="Permalink to this definition">¶</a></dt>
<dd><p>The name of the Log Analytics Workspace where the Log Analytics Windows Performance Counter DataSource should exist. Changing this forces a new Log Analytics Windows Performance Counter DataSource to be created.</p>
</dd></dl>

<dl class="py method">
<dt id="pulumi_azure.loganalytics.DataSourceWindowsPerformanceCounter.get">
<em class="property">static </em><code class="sig-name descname">get</code><span class="sig-paren">(</span><em class="sig-param"><span class="n">resource_name</span></em>, <em class="sig-param"><span class="n">id</span></em>, <em class="sig-param"><span class="n">opts</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">counter_name</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">instance_name</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">interval_seconds</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">name</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">object_name</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">resource_group_name</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">workspace_name</span><span class="o">=</span><span class="default_value">None</span></em><span class="sig-paren">)</span><a class="headerlink" href="#pulumi_azure.loganalytics.DataSourceWindowsPerformanceCounter.get" title="Permalink to this definition">¶</a></dt>
<dd><p>Get an existing DataSourceWindowsPerformanceCounter resource’s state with the given name, id, and optional extra
properties used to qualify the lookup.</p>
<dl class="field-list simple">
<dt class="field-odd">Parameters</dt>
<dd class="field-odd"><ul class="simple">
<li><p><strong>resource_name</strong> (<em>str</em>) – The unique name of the resulting resource.</p></li>
<li><p><strong>id</strong> (<em>str</em>) – The unique provider ID of the resource to lookup.</p></li>
<li><p><strong>opts</strong> (<a class="reference internal" href="../../pulumi/#pulumi.ResourceOptions" title="pulumi.ResourceOptions"><em>pulumi.ResourceOptions</em></a>) – Options for the resource.</p></li>
<li><p><strong>counter_name</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – The friendly name of the performance counter.</p></li>
<li><p><strong>instance_name</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – The name of the virtual machine instance to which the Windows Performance Counter DataSource be applied. Specify a <code class="docutils literal notranslate"><span class="pre">*</span></code> will apply to all instances.</p></li>
<li><p><strong>interval_seconds</strong> (<em>pulumi.Input</em><em>[</em><em>float</em><em>]</em>) – The time of sample interval in seconds. Supports values between 10 and 2147483647.</p></li>
<li><p><strong>name</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – The Name which should be used for this Log Analytics Windows Performance Counter DataSource. Changing this forces a new Log Analytics Windows Performance Counter DataSource to be created.</p></li>
<li><p><strong>object_name</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – The object name of the Log Analytics Windows Performance Counter DataSource.</p></li>
<li><p><strong>resource_group_name</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – The name of the Resource Group where the Log Analytics Windows Performance Counter DataSource should exist. Changing this forces a new Log Analytics Windows Performance Counter DataSource to be created.</p></li>
<li><p><strong>workspace_name</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – The name of the Log Analytics Workspace where the Log Analytics Windows Performance Counter DataSource should exist. Changing this forces a new Log Analytics Windows Performance Counter DataSource to be created.</p></li>
</ul>
</dd>
</dl>
</dd></dl>

<dl class="py method">
<dt id="pulumi_azure.loganalytics.DataSourceWindowsPerformanceCounter.translate_output_property">
<code class="sig-name descname">translate_output_property</code><span class="sig-paren">(</span><em class="sig-param"><span class="n">prop</span></em><span class="sig-paren">)</span><a class="headerlink" href="#pulumi_azure.loganalytics.DataSourceWindowsPerformanceCounter.translate_output_property" title="Permalink to this definition">¶</a></dt>
<dd><p>Provides subclasses of Resource an opportunity to translate names of output properties
into a format of their choosing before writing those properties to the resource object.</p>
<dl class="field-list simple">
<dt class="field-odd">Parameters</dt>
<dd class="field-odd"><p><strong>prop</strong> (<em>str</em>) – A property name.</p>
</dd>
<dt class="field-even">Returns</dt>
<dd class="field-even"><p>A potentially transformed property name.</p>
</dd>
<dt class="field-odd">Return type</dt>
<dd class="field-odd"><p>str</p>
</dd>
</dl>
</dd></dl>

<dl class="py method">
<dt id="pulumi_azure.loganalytics.DataSourceWindowsPerformanceCounter.translate_input_property">
<code class="sig-name descname">translate_input_property</code><span class="sig-paren">(</span><em class="sig-param"><span class="n">prop</span></em><span class="sig-paren">)</span><a class="headerlink" href="#pulumi_azure.loganalytics.DataSourceWindowsPerformanceCounter.translate_input_property" title="Permalink to this definition">¶</a></dt>
<dd><p>Provides subclasses of Resource an opportunity to translate names of input properties into
a format of their choosing before sending those properties to the Pulumi engine.</p>
<dl class="field-list simple">
<dt class="field-odd">Parameters</dt>
<dd class="field-odd"><p><strong>prop</strong> (<em>str</em>) – A property name.</p>
</dd>
<dt class="field-even">Returns</dt>
<dd class="field-even"><p>A potentially transformed property name.</p>
</dd>
<dt class="field-odd">Return type</dt>
<dd class="field-odd"><p>str</p>
</dd>
</dl>
</dd></dl>

</dd></dl>

<dl class="py class">
<dt id="pulumi_azure.loganalytics.LinkedService">
<em class="property">class </em><code class="sig-prename descclassname">pulumi_azure.loganalytics.</code><code class="sig-name descname">LinkedService</code><span class="sig-paren">(</span><em class="sig-param"><span class="n">resource_name</span></em>, <em class="sig-param"><span class="n">opts</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">linked_service_name</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">resource_group_name</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">resource_id</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">tags</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">workspace_name</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">__props__</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">__name__</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">__opts__</span><span class="o">=</span><span class="default_value">None</span></em><span class="sig-paren">)</span><a class="headerlink" href="#pulumi_azure.loganalytics.LinkedService" title="Permalink to this definition">¶</a></dt>
<dd><p>Links a Log Analytics (formally Operational Insights) Workspace to another resource. The (currently) only linkable service is an Azure Automation Account.</p>
<div class="highlight-python notranslate"><div class="highlight"><pre><span></span><span class="kn">import</span> <span class="nn">pulumi</span>
<span class="kn">import</span> <span class="nn">pulumi_azure</span> <span class="k">as</span> <span class="nn">azure</span>

<span class="n">example_resource_group</span> <span class="o">=</span> <span class="n">azure</span><span class="o">.</span><span class="n">core</span><span class="o">.</span><span class="n">ResourceGroup</span><span class="p">(</span><span class="s2">&quot;exampleResourceGroup&quot;</span><span class="p">,</span> <span class="n">location</span><span class="o">=</span><span class="s2">&quot;West Europe&quot;</span><span class="p">)</span>
<span class="n">example_account</span> <span class="o">=</span> <span class="n">azure</span><span class="o">.</span><span class="n">automation</span><span class="o">.</span><span class="n">Account</span><span class="p">(</span><span class="s2">&quot;exampleAccount&quot;</span><span class="p">,</span>
    <span class="n">location</span><span class="o">=</span><span class="n">example_resource_group</span><span class="o">.</span><span class="n">location</span><span class="p">,</span>
    <span class="n">resource_group_name</span><span class="o">=</span><span class="n">example_resource_group</span><span class="o">.</span><span class="n">name</span><span class="p">,</span>
    <span class="n">sku</span><span class="o">=</span><span class="p">[{</span>
        <span class="s2">&quot;name&quot;</span><span class="p">:</span> <span class="s2">&quot;Basic&quot;</span><span class="p">,</span>
    <span class="p">}],</span>
    <span class="n">tags</span><span class="o">=</span><span class="p">{</span>
        <span class="s2">&quot;environment&quot;</span><span class="p">:</span> <span class="s2">&quot;development&quot;</span><span class="p">,</span>
    <span class="p">})</span>
<span class="n">example_analytics_workspace</span> <span class="o">=</span> <span class="n">azure</span><span class="o">.</span><span class="n">operationalinsights</span><span class="o">.</span><span class="n">AnalyticsWorkspace</span><span class="p">(</span><span class="s2">&quot;exampleAnalyticsWorkspace&quot;</span><span class="p">,</span>
    <span class="n">location</span><span class="o">=</span><span class="n">example_resource_group</span><span class="o">.</span><span class="n">location</span><span class="p">,</span>
    <span class="n">resource_group_name</span><span class="o">=</span><span class="n">example_resource_group</span><span class="o">.</span><span class="n">name</span><span class="p">,</span>
    <span class="n">sku</span><span class="o">=</span><span class="s2">&quot;PerGB2018&quot;</span><span class="p">,</span>
    <span class="n">retention_in_days</span><span class="o">=</span><span class="mi">30</span><span class="p">)</span>
<span class="n">example_linked_service</span> <span class="o">=</span> <span class="n">azure</span><span class="o">.</span><span class="n">loganalytics</span><span class="o">.</span><span class="n">LinkedService</span><span class="p">(</span><span class="s2">&quot;exampleLinkedService&quot;</span><span class="p">,</span>
    <span class="n">resource_group_name</span><span class="o">=</span><span class="n">example_resource_group</span><span class="o">.</span><span class="n">name</span><span class="p">,</span>
    <span class="n">workspace_name</span><span class="o">=</span><span class="n">example_analytics_workspace</span><span class="o">.</span><span class="n">name</span><span class="p">,</span>
    <span class="n">resource_id</span><span class="o">=</span><span class="n">example_account</span><span class="o">.</span><span class="n">id</span><span class="p">)</span>
</pre></div>
</div>
<dl class="field-list simple">
<dt class="field-odd">Parameters</dt>
<dd class="field-odd"><ul class="simple">
<li><p><strong>resource_name</strong> (<em>str</em>) – The name of the resource.</p></li>
<li><p><strong>opts</strong> (<a class="reference internal" href="../../pulumi/#pulumi.ResourceOptions" title="pulumi.ResourceOptions"><em>pulumi.ResourceOptions</em></a>) – Options for the resource.</p></li>
<li><p><strong>linked_service_name</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – Name of the type of linkedServices resource to connect to the Log Analytics Workspace specified in <code class="docutils literal notranslate"><span class="pre">workspace_name</span></code>. Currently it defaults to and only supports <code class="docutils literal notranslate"><span class="pre">automation</span></code> as a value. Changing this forces a new resource to be created.</p></li>
<li><p><strong>resource_group_name</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – The name of the resource group in which the Log Analytics Linked Service is created. Changing this forces a new resource to be created.</p></li>
<li><p><strong>resource_id</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – The ID of the Resource that will be linked to the workspace. Changing this forces a new resource to be created.</p></li>
<li><p><strong>tags</strong> (<em>pulumi.Input</em><em>[</em><em>dict</em><em>]</em>) – A mapping of tags to assign to the resource.</p></li>
<li><p><strong>workspace_name</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – Name of the Log Analytics Workspace that will contain the linkedServices resource. Changing this forces a new resource to be created.</p></li>
</ul>
</dd>
</dl>
<dl class="py attribute">
<dt id="pulumi_azure.loganalytics.LinkedService.linked_service_name">
<code class="sig-name descname">linked_service_name</code><em class="property">: pulumi.Output[str]</em><em class="property"> = None</em><a class="headerlink" href="#pulumi_azure.loganalytics.LinkedService.linked_service_name" title="Permalink to this definition">¶</a></dt>
<dd><p>Name of the type of linkedServices resource to connect to the Log Analytics Workspace specified in <code class="docutils literal notranslate"><span class="pre">workspace_name</span></code>. Currently it defaults to and only supports <code class="docutils literal notranslate"><span class="pre">automation</span></code> as a value. Changing this forces a new resource to be created.</p>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_azure.loganalytics.LinkedService.name">
<code class="sig-name descname">name</code><em class="property">: pulumi.Output[str]</em><em class="property"> = None</em><a class="headerlink" href="#pulumi_azure.loganalytics.LinkedService.name" title="Permalink to this definition">¶</a></dt>
<dd><p>The automatically generated name of the Linked Service. This cannot be specified. The format is always <code class="docutils literal notranslate"><span class="pre">&lt;workspace_name&gt;/&lt;linked_service_name&gt;</span></code> e.g. <code class="docutils literal notranslate"><span class="pre">workspace1/Automation</span></code></p>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_azure.loganalytics.LinkedService.resource_group_name">
<code class="sig-name descname">resource_group_name</code><em class="property">: pulumi.Output[str]</em><em class="property"> = None</em><a class="headerlink" href="#pulumi_azure.loganalytics.LinkedService.resource_group_name" title="Permalink to this definition">¶</a></dt>
<dd><p>The name of the resource group in which the Log Analytics Linked Service is created. Changing this forces a new resource to be created.</p>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_azure.loganalytics.LinkedService.resource_id">
<code class="sig-name descname">resource_id</code><em class="property">: pulumi.Output[str]</em><em class="property"> = None</em><a class="headerlink" href="#pulumi_azure.loganalytics.LinkedService.resource_id" title="Permalink to this definition">¶</a></dt>
<dd><p>The ID of the Resource that will be linked to the workspace. Changing this forces a new resource to be created.</p>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_azure.loganalytics.LinkedService.tags">
<code class="sig-name descname">tags</code><em class="property">: pulumi.Output[dict]</em><em class="property"> = None</em><a class="headerlink" href="#pulumi_azure.loganalytics.LinkedService.tags" title="Permalink to this definition">¶</a></dt>
<dd><p>A mapping of tags to assign to the resource.</p>
</dd></dl>

<dl class="py attribute">
<dt id="pulumi_azure.loganalytics.LinkedService.workspace_name">
<code class="sig-name descname">workspace_name</code><em class="property">: pulumi.Output[str]</em><em class="property"> = None</em><a class="headerlink" href="#pulumi_azure.loganalytics.LinkedService.workspace_name" title="Permalink to this definition">¶</a></dt>
<dd><p>Name of the Log Analytics Workspace that will contain the linkedServices resource. Changing this forces a new resource to be created.</p>
</dd></dl>

<dl class="py method">
<dt id="pulumi_azure.loganalytics.LinkedService.get">
<em class="property">static </em><code class="sig-name descname">get</code><span class="sig-paren">(</span><em class="sig-param"><span class="n">resource_name</span></em>, <em class="sig-param"><span class="n">id</span></em>, <em class="sig-param"><span class="n">opts</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">linked_service_name</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">name</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">resource_group_name</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">resource_id</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">tags</span><span class="o">=</span><span class="default_value">None</span></em>, <em class="sig-param"><span class="n">workspace_name</span><span class="o">=</span><span class="default_value">None</span></em><span class="sig-paren">)</span><a class="headerlink" href="#pulumi_azure.loganalytics.LinkedService.get" title="Permalink to this definition">¶</a></dt>
<dd><p>Get an existing LinkedService resource’s state with the given name, id, and optional extra
properties used to qualify the lookup.</p>
<dl class="field-list simple">
<dt class="field-odd">Parameters</dt>
<dd class="field-odd"><ul class="simple">
<li><p><strong>resource_name</strong> (<em>str</em>) – The unique name of the resulting resource.</p></li>
<li><p><strong>id</strong> (<em>str</em>) – The unique provider ID of the resource to lookup.</p></li>
<li><p><strong>opts</strong> (<a class="reference internal" href="../../pulumi/#pulumi.ResourceOptions" title="pulumi.ResourceOptions"><em>pulumi.ResourceOptions</em></a>) – Options for the resource.</p></li>
<li><p><strong>linked_service_name</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – Name of the type of linkedServices resource to connect to the Log Analytics Workspace specified in <code class="docutils literal notranslate"><span class="pre">workspace_name</span></code>. Currently it defaults to and only supports <code class="docutils literal notranslate"><span class="pre">automation</span></code> as a value. Changing this forces a new resource to be created.</p></li>
<li><p><strong>name</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – The automatically generated name of the Linked Service. This cannot be specified. The format is always <code class="docutils literal notranslate"><span class="pre">&lt;workspace_name&gt;/&lt;linked_service_name&gt;</span></code> e.g. <code class="docutils literal notranslate"><span class="pre">workspace1/Automation</span></code></p></li>
<li><p><strong>resource_group_name</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – The name of the resource group in which the Log Analytics Linked Service is created. Changing this forces a new resource to be created.</p></li>
<li><p><strong>resource_id</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – The ID of the Resource that will be linked to the workspace. Changing this forces a new resource to be created.</p></li>
<li><p><strong>tags</strong> (<em>pulumi.Input</em><em>[</em><em>dict</em><em>]</em>) – A mapping of tags to assign to the resource.</p></li>
<li><p><strong>workspace_name</strong> (<em>pulumi.Input</em><em>[</em><em>str</em><em>]</em>) – Name of the Log Analytics Workspace that will contain the linkedServices resource. Changing this forces a new resource to be created.</p></li>
</ul>
</dd>
</dl>
</dd></dl>

<dl class="py method">
<dt id="pulumi_azure.loganalytics.LinkedService.translate_output_property">
<code class="sig-name descname">translate_output_property</code><span class="sig-paren">(</span><em class="sig-param"><span class="n">prop</span></em><span class="sig-paren">)</span><a class="headerlink" href="#pulumi_azure.loganalytics.LinkedService.translate_output_property" title="Permalink to this definition">¶</a></dt>
<dd><p>Provides subclasses of Resource an opportunity to translate names of output properties
into a format of their choosing before writing those properties to the resource object.</p>
<dl class="field-list simple">
<dt class="field-odd">Parameters</dt>
<dd class="field-odd"><p><strong>prop</strong> (<em>str</em>) – A property name.</p>
</dd>
<dt class="field-even">Returns</dt>
<dd class="field-even"><p>A potentially transformed property name.</p>
</dd>
<dt class="field-odd">Return type</dt>
<dd class="field-odd"><p>str</p>
</dd>
</dl>
</dd></dl>

<dl class="py method">
<dt id="pulumi_azure.loganalytics.LinkedService.translate_input_property">
<code class="sig-name descname">translate_input_property</code><span class="sig-paren">(</span><em class="sig-param"><span class="n">prop</span></em><span class="sig-paren">)</span><a class="headerlink" href="#pulumi_azure.loganalytics.LinkedService.translate_input_property" title="Permalink to this definition">¶</a></dt>
<dd><p>Provides subclasses of Resource an opportunity to translate names of input properties into
a format of their choosing before sending those properties to the Pulumi engine.</p>
<dl class="field-list simple">
<dt class="field-odd">Parameters</dt>
<dd class="field-odd"><p><strong>prop</strong> (<em>str</em>) – A property name.</p>
</dd>
<dt class="field-even">Returns</dt>
<dd class="field-even"><p>A potentially transformed property name.</p>
</dd>
<dt class="field-odd">Return type</dt>
<dd class="field-odd"><p>str</p>
</dd>
</dl>
</dd></dl>

</dd></dl>

</div>
