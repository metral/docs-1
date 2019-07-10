---
title: Module serverless
---

<!-- WARNING: this page was generated by a tool. Do not edit it by hand. -->
<!-- To change it, please see https://github.com/pulumi/docs/tree/master/tools/tscdocgen. -->

<a href="../">@pulumi/aws</a> &gt; serverless

> This provider is a derived work of the [Terraform Provider](https://github.com/terraform-providers/terraform-provider-aws)
> distributed under [MPL 2.0](https://www.mozilla.org/en-US/MPL/2.0/). If you encounter a bug or missing feature,
> first check the [`pulumi/pulumi-aws` repo](https://github.com/pulumi/pulumi-aws/issues); however, if that doesn't turn up anything,
> please consult the source [`terraform-providers/terraform-provider-aws` repo](https://github.com/terraform-providers/terraform-provider-aws/issues).



<div class="toggleVisible">
<div class="collapsed">
<h2 class="pdoc-module-header toggleButton" title="Click to show Index">Index ▹</h2>
</div>
<div class="expanded">
<h2 class="pdoc-module-header toggleButton" title="Click to hide Index">Index ▾</h2>
<div class="pdoc-module-contents">
<ul>
<li><a href="#Function">class Function</a></li>
<li><a href="#Context">type Context</a></li>
<li><a href="#FunctionOptions">type FunctionOptions</a></li>
<li><a href="#Handler">type Handler</a></li>
<li><a href="#HandlerFactory">type HandlerFactory</a></li>
</ul>

<a href="https://github.com/pulumi/pulumi-aws/blob/35faf389944ec00da164b2681656a982bf699412/sdk/nodejs/serverless/function.ts">serverless/function.ts</a> 
</div>
</div>
</div>


<h2 class="pdoc-module-header" id="Function">
<a class="pdoc-member-name" href="https://github.com/pulumi/pulumi-aws/blob/35faf389944ec00da164b2681656a982bf699412/sdk/nodejs/serverless/function.ts#L94">class <b>Function</b></a>
</h2>
<div class="pdoc-module-contents">
<pre class="highlight"><span class='kd'>extends</span> <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#ComponentResource'>ComponentResource</a></pre>
{{% md %}}

Function is a higher-level API for creating and managing AWS Lambda Function resources
implemented by a Pulumi lambda expression and with a set of attached policies.

{{% /md %}}
<h3 class="pdoc-member-header" id="Function-constructor">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/35faf389944ec00da164b2681656a982bf699412/sdk/nodejs/serverless/function.ts#L97"> <b>constructor</b></a>
</h3>
<div class="pdoc-member-contents">
{{% md %}}

<pre class="highlight"><span class='kd'></span><span class='kd'>new</span> Function(name: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>, options: <a href='#FunctionOptions'>FunctionOptions</a>, func?: <a href='#Handler'>Handler</a>, opts?: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#ResourceOptions'>pulumi.ResourceOptions</a>)</pre>

* `func` Deprecated.  Pass the function as [options.func] or [options.factoryFunc] instead.

{{% /md %}}
</div>
<h3 class="pdoc-member-header" id="Function-getProvider">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/35faf389944ec00da164b2681656a982bf699412/sdk/nodejs/node_modules/@pulumi/pulumi/resource.d.ts#L19">method <b>getProvider</b></a>
</h3>
<div class="pdoc-member-contents">
{{% md %}}

<pre class="highlight"><span class='kd'></span>getProvider(moduleMember: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>): ProviderResource | <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined'>undefined</a></span></pre>

{{% /md %}}
</div>
<h3 class="pdoc-member-header" id="Function-isInstance">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/35faf389944ec00da164b2681656a982bf699412/sdk/nodejs/node_modules/@pulumi/pulumi/resource.d.ts#L233">method <b>isInstance</b></a>
</h3>
<div class="pdoc-member-contents">
{{% md %}}

<pre class="highlight"><span class='kd'>static </span>isInstance(obj: <span class='kd'><a href='https://www.typescriptlang.org/docs/handbook/basic-types.html#any'>any</a></span>): <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean'>boolean</a></span></pre>


Returns true if the given object is an instance of CustomResource.  This is designed to work even when
multiple copies of the Pulumi SDK have been loaded into the same process.

{{% /md %}}
</div>
<h3 class="pdoc-member-header" id="Function-registerOutputs">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/35faf389944ec00da164b2681656a982bf699412/sdk/nodejs/node_modules/@pulumi/pulumi/resource.d.ts#L248">method <b>registerOutputs</b></a>
</h3>
<div class="pdoc-member-contents">
{{% md %}}

<pre class="highlight"><span class='kd'>protected </span>registerOutputs(outputs?: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Inputs'>Inputs</a> | <a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise'>Promise</a>&lt;<a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Inputs'>Inputs</a>&gt; | <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Output'>Output</a>&lt;<a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Inputs'>Inputs</a>&gt;): <span class='kd'><a href='https://www.typescriptlang.org/docs/handbook/basic-types.html#void'>void</a></span></pre>

{{% /md %}}
</div>
<h3 class="pdoc-member-header" id="Function-lambda">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/35faf389944ec00da164b2681656a982bf699412/sdk/nodejs/serverless/function.ts#L96">property <b>lambda</b></a>
</h3>
<div class="pdoc-member-contents">
<pre class="highlight"><span class='kd'>public </span>lambda: lambda.Function;</pre>
{{% md %}}
{{% /md %}}
</div>
<h3 class="pdoc-member-header" id="Function-options">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/35faf389944ec00da164b2681656a982bf699412/sdk/nodejs/serverless/function.ts#L95">property <b>options</b></a>
</h3>
<div class="pdoc-member-contents">
<pre class="highlight"><span class='kd'>public </span>options: <a href='#FunctionOptions'>FunctionOptions</a>;</pre>
{{% md %}}
{{% /md %}}
</div>
<h3 class="pdoc-member-header" id="Function-role">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/35faf389944ec00da164b2681656a982bf699412/sdk/nodejs/serverless/function.ts#L97">property <b>role</b></a>
</h3>
<div class="pdoc-member-contents">
<pre class="highlight"><span class='kd'>public </span>role: <a href='#Role'>Role</a> | <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined'>undefined</a></span>;</pre>
{{% md %}}
{{% /md %}}
</div>
<h3 class="pdoc-member-header" id="Function-urn">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/35faf389944ec00da164b2681656a982bf699412/sdk/nodejs/node_modules/@pulumi/pulumi/resource.d.ts#L17">property <b>urn</b></a>
</h3>
<div class="pdoc-member-contents">
<pre class="highlight"><span class='kd'></span>urn: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Output'>Output</a>&lt;<a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#URN'>URN</a>&gt;;</pre>
{{% md %}}

urn is the stable logical URN used to distinctly address a resource, both before and after
deployments.

{{% /md %}}
</div>
</div>
<h2 class="pdoc-module-header" id="Context">
<a class="pdoc-member-name" href="https://github.com/pulumi/pulumi-aws/blob/35faf389944ec00da164b2681656a982bf699412/sdk/nodejs/serverless/function.ts#L23">type <b>Context</b></a>
</h2>
<div class="pdoc-module-contents">
<pre class="highlight"><span class='kd'>type</span> Context = lambda.Context;</pre>
</div>
<h2 class="pdoc-module-header" id="FunctionOptions">
<a class="pdoc-member-name" href="https://github.com/pulumi/pulumi-aws/blob/35faf389944ec00da164b2681656a982bf699412/sdk/nodejs/serverless/function.ts#L51">type <b>FunctionOptions</b></a>
</h2>
<div class="pdoc-module-contents">
<pre class="highlight"><span class='kd'>type</span> FunctionOptions = utils.Overwrite&lt;lambda.CallbackFunctionArgs&lt;<span class='kd'><a href='https://www.typescriptlang.org/docs/handbook/basic-types.html#any'>any</a></span>, <span class='kd'><a href='https://www.typescriptlang.org/docs/handbook/basic-types.html#any'>any</a></span>&gt;, {
    excludePackages: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>[];
    factoryFunc: <a href='#HandlerFactory'>HandlerFactory</a>;
    func: <a href='#Handler'>Handler</a>;
    includePackages: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>[];
    includePaths: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>[];
}&gt;;</pre>
{{% md %}}

FunctionOptions provides configuration options for the serverless Function.  It is effectively
equivalent to [aws.lambda.FunctionArgs] except with a few important differences documented at the
property level.  For example, [role] is an actual iam.Role instance, and not an ARN. Properties
like [runtime] are now optional.  And some properties (like [code]) are entirely disallowed.

{{% /md %}}
</div>
<h2 class="pdoc-module-header" id="Handler">
<a class="pdoc-member-name" href="https://github.com/pulumi/pulumi-aws/blob/35faf389944ec00da164b2681656a982bf699412/sdk/nodejs/serverless/function.ts#L31">type <b>Handler</b></a>
</h2>
<div class="pdoc-module-contents">
<pre class="highlight"><span class='kd'>type</span> Handler = lambda.Callback&lt;<span class='kd'><a href='https://www.typescriptlang.org/docs/handbook/basic-types.html#any'>any</a></span>, <span class='kd'><a href='https://www.typescriptlang.org/docs/handbook/basic-types.html#any'>any</a></span>&gt;;</pre>
{{% md %}}

[Handler] is the signature for a serverless function that will be invoked each time the AWS
Lambda is invoked.

{{% /md %}}
</div>
<h2 class="pdoc-module-header" id="HandlerFactory">
<a class="pdoc-member-name" href="https://github.com/pulumi/pulumi-aws/blob/35faf389944ec00da164b2681656a982bf699412/sdk/nodejs/serverless/function.ts#L41">type <b>HandlerFactory</b></a>
</h2>
<div class="pdoc-module-contents">
<pre class="highlight"><span class='kd'>type</span> HandlerFactory = () => <a href='#Handler'>Handler</a>;</pre>
{{% md %}}

HandlerFactory is the signature for a function that will be called once to produce the serverless
function that AWS Lambda will invoke.  It can be used to initialize expensive state once that can
then be used across all invocations of the Lambda (as long as the Lambda is using the same warm
node instance).

{{% /md %}}
</div>