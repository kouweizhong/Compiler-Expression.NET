---
layout: post
---

<html lang="en">
	<head>
		<meta charset="utf-8">
		<meta name="viewport" content="width=device-width, initial-scale=1">
		<meta http-equiv="x-ua-compatible" content="ie=edge">
		<meta name="description" content="Evaluate, Compile and Execute C# code and expression at runtime">
		<meta name="keywords" content=".NET, dotnet, C#, CSharp, VB, Eval, Evaluate, Compile, Execute, Expression, Dynamic, Runtime">
		<title>Evaluate, Compile and Execute C# code and expression at runtime</title>
		<link rel="icon" type="image/png" href="http://eval-expression.net/images/logo.png">
		<link rel="stylesheet" type="text/css" href="https://cdn.rawgit.com/twbs/bootstrap/v4-dev/dist/css/bootstrap.min.css">
		<link rel="stylesheet" type="text/css" href="https://maxcdn.bootstrapcdn.com/font-awesome/4.4.0/css/font-awesome.min.css">
		<link rel="stylesheet" type="text/css" href="/css/github.css">
	</head>
	
	<body>
		<!-- anchor !-->
		<a id="download" href="#"></a>
		<a id="github" href="#"></a>
		
		<!-- top-header !-->
		<div id="top-header">
			<div class="container">
				<div class="text-right">
					<a href="mailto:sales@zzzprojects.com"><i class="fa fa-envelope"></i>&nbsp;&nbsp;sales@zzzprojects.com</a>
					<a href="https://www.facebook.com/zzzprojects" target="_blank"><i class="fa fa-facebook"></i></a>
					<a href="https://twitter.com/zzzprojects" target="_blank"><i class="fa fa-twitter"></i></a>
					<a href="https://plus.google.com/+Zzzprojects_NetSQL/posts" target="_blank"><i class="fa fa-google-plus"></i></a>
					<a href="http://zzzprojects.us9.list-manage.com/subscribe?u=cecbc4775cf67bf1ff82018af&id=4765ffa5f8" target="_blank" class="hidden-sm-down"><i class="fa fa-newspaper-o"></i></a>
				</div>
			</div>
		</div>
		
		<!-- header !-->
		<header>
			<div class="container">
				<div class="row">
					<div class="col-lg-6">
						<div class="card">
							<div class="card-block">
								<h1 class="card-title">Eval Expression.NET</h1>
								<h3>Evaluate, Compile and Execute C# code and expression at runtime</h3>
								<hr class="m-y-md" />
								<div class="lead">
									<a href="https://www.nuget.org/packages/Z.Expressions.Eval/" target="_blank" class="btn btn-success btn-lg btn-left" role="button"><span><i class="fa fa-cloud-download fa-2x"></i>&nbsp;<span>Download</span></span></a>
									<a href="https://github.com/zzzprojects/Eval-Expression.NET" target="_blank" class="btn btn-primary btn-lg btn-right" role="button"><span><i class="fa fa-github fa-2x"></i>&nbsp;<span>GitHub</span></span></a>
									<p class="text-muted">* FREE Version - up to 50 characters</p>						
								</div>
							</div>
						</div>
					</div>
					<div class="col-lg-6">
						<div class="card">
							<div class="card-block card-code">
{% highlight csharp %}
// From simple expression...
int result = Eval.Execute<int>("X + Y", new { X = 1, Y = 2})

// To complex code.
int result = Eval.Execute<int>(@"
	var list = new List<int>() { 1..100 };
	var filter = list.Where(x => x < 3);
	return result.Sum(x => x);");
	
// Support full C# Syntax including:
// - Anonymous Type
// - Extension Methods
// - Generic Type
{% endhighlight %}	
							</div>
						</div>
					</div>
				</div>
			</div>
		</header>
		
		<!-- anchor !-->
		<a id="features" href="#"></a>
		
		<!-- features !-->
		<div id="feature">
			<div class="container">
				<div class="row">
					<div class="col-lg-6">
						<!-- anchor !-->
						<a id="eval_execute" href="#"></a>
						<h2>Eval.Execute</h2>
						<hr class="m-y-md" />
						<div class="block-code">
							<p>Evaluate and execute the code or expression</p>
							<h3>Anonymous Class</h3>
{% highlight csharp %}
int result = Eval.Execute<int>("X + Y", new { X = 1, Y = 2});
{% endhighlight %}
							<h3>Class Member</h3>
{% highlight csharp %}
dynamic expandoObject = new ExpandoObject();
expandoObject.X = 1;
expandoObject.Y = 2;
int result = Eval.Execute<int>("X + Y", expandoObject);
{% endhighlight %}
							<h3>Argument Position</h3>
{% highlight csharp %}
int result = Eval.Execute<int>("{0} + {1}", 1, 2);
{% endhighlight %}
							<h3>Extension Methods</h3>
{% highlight csharp %}
string s = "X + Y";
int result = s.Execute<int>(code, new { X = 1, Y = 2});
{% endhighlight %}
						</div>
					</div>
					<div class="col-lg-6">
						<!-- anchor !-->
						<a id="eval_compile" href="#"></a>
						<h2>Eval.Compile</h2>
						<hr class="m-y-md" />
						<div class="block-code">
							<p>Compile the code or expression and return a delegate</p>
							<h3>Custom Delegate</h3>
{% highlight csharp %}
string code = "Price * Quantity";
var compiled = Eval.Compile<Func<OrderItem, decimal>>(code);

decimal totals = 0;
foreach(var item in list)
{
    totals += compiled(item);
}
{% endhighlight %}
							<h3>Extension Methods</h3>
{% highlight csharp %}
string s = "Price * Quantity";
var compiled = s.Compile<Func<OrderItem, decimal>>(code);

decimal totals = 0;
foreach(var item in list)
{
    totals += compiled(item);
}
{% endhighlight %}
						</div>
					</div>
				</div>
				<div class="text-center">
					<a class="btn btn-primary btn-lg" href="https://github.com/zzzprojects/Eval-Expression.NET/wiki" role="button" target="_blank">Learn More&nbsp;<i class="fa fa-hand-o-right"></i></a>
				</div>
			</div>
		</div>
		
		<!-- anchor !-->
		<a id="pro" href="#"></a>
		
		<!-- pricing !-->
		<div id="pricing">
			<div class="container">
				<div class="row">
					<div class="col-lg-6">
						<h2>Pricing</h2>
						<hr class="m-y-md" />
						<p>Become a <span class="text-bold text-green">PRO</span> now and start saving time and money!</p>
						<p>Thousands of <span class="text-bold">development hours</span> and thousands of <span class="text-bold">unit tests</span> to make Eval Expression.NET the best and most robust C# expression evaluator.</p>
						<p>
							PRO License starting at <span class="text-bold text-green">ONLY $299</span>
							<br />
							<span class="text-muted">+$100/Additional developer seat</span>
						</p>
						<hr class="m-y-md" />
						<p>With the free version comes a month long trial of the pro license to let you evaluate all its functonalities without limits.</p>
												
					</div>
					<div class="col-lg-6">
						<table class="table table-hover table-bordered">
							<thead class="thead-inverse">
								<tr>
									<th></th>
									<th>FREE</th>
									<th>PRO</th>
								</tr>
							</thead>
							<tbody>
								<tr>
									<th>Maximum Characters</th>
									<td>50</td>
									<td>Unlimited</td>
								</tr>
								<tr>
									<th>Commercial License</th>
									<td><i class="fa fa-times fa-2x"></i></td>
									<td><i class="fa fa-check-square-o fa-2x"></i></td>
								</tr>
								<tr>
									<th>Royalty-Free</th>
									<td><i class="fa fa-times fa-2x"></i></td>
									<td><i class="fa fa-check-square-o fa-2x"></i></td>
								</tr>
								<tr>
									<th>Support & Upgrades (1 year)</th>
									<td><i class="fa fa-times fa-2x"></i></td>
									<td><i class="fa fa-check-square-o fa-2x"></i></td>
								</tr>
							</tbody>
						</table>
						
						<form action="https://www.paypal.com/cgi-bin/webscr" method="post" target="_top" onsubmit="return purchase_validate()">
							<input type="hidden" name="cmd" value="_s-xclick">
							<input type="hidden" name="hosted_button_id" value="PW79CTHBQFBZC">
							<input type="hidden" name="currency_code" value="USD">
							<fieldset class="form-group">
								<input type="hidden" name="on0" value="Seats">
								<select name="os0" class="form-control">
									<option value="1 seat">Eval Expression.NET $299 (1 seat)</option>
									<option value="2 seats">Eval Expression.NET $399 (2 seats)</option>
									<option value="3 seats">Eval Expression.NET $499 (3 seats)</option>
									<option value="4 seats">Eval Expression.NET $599 (4 seats)</option>
									<option value="5-9 seats">Eval Expression.NET $699 (5-9 seats)</option>
									<option value="10-15 seats">Eval Expression.NET $899 (10-15 seats)</option>
								</select> 
							</fieldset>
							<div class="checkbox">
								<label>
									<input id="agree_agreement" type="checkbox">I have read and agree to the <a href="http://www.zzzprojects.com/license-agreement/" target="_blank">License Agreement</a>.
								</label>
							</div>
							<button type="submit" class="btn btn-success btn-lg"><span><i class="fa fa-shopping-cart"></i>&nbsp;<span>BUY NOW</span></span></button>
						</form>					
					</div>
				</div>
			</div>
			
			<!-- validation !-->
			<div id="error_validation" class="modal fade" tabindex="-1" role="dialog" aria-labelledby="modal_agreement" aria-hidden="true">
				<div class="modal-dialog" role="document">
					<div class="modal-content">
						<div class="modal-header">
							<h4 class="modal-title" id="modal_agreement">License Agreement</h4>
						</div>
						<div class="modal-body bg-danger">
							You must read and agree to the License Agreement.
						</div>
						<div class="modal-footer">
							<button type="button" class="btn btn-secondary" data-dismiss="modal">Close</button>
						</div>
					</div>
				</div>
			</div>
		</div>

		<!-- support !-->
		<div id="support">
			<div class="container">
				<h2>Test our Outstanding Support</h2>
				<h3>We usually answer within the next business day, hour, or minutes!</h3>
				<div class="row">
					<hr class="hidden-sm-up" />
					<div class="col-sm-6 col-lg-3">
						<div class="card">
							<div class="card-block">
								<h4 class="card-title">Documentation</h4>
							</div>
							<a href="https://github.com/zzzprojects/Eval-Expression.NET/wiki" target="_blank"><i class="fa fa-folder-open fa-5x"></i></a>
							<div class="card-block">
								<p class="card-text">Consult our complete documentation to help you getting started.</p>
								<a href="https://github.com/zzzprojects/Eval-Expression.NET/wiki" target="_blank">Documentation</a>
							</div>
						</div>
					</div>
					<hr class="hidden-sm-up" />
					<div class="col-sm-6 col-lg-3">
						<div class="card">
							<div class="card-block">
								<h4 class="card-title">Contact Us</h4>
							</div>
							<a href="mailto:sales@zzzprojects.com"><i class="fa fa-users fa-5x"></i></a>
							<div class="card-block">
								<p class="card-text">Email our team for any type of questions. We love to hear from you!</p>
								<a href="mailto:sales@zzzprojects.com">sales@zzzprojects.com</a>
							</div>
						</div>
					</div>
					<hr class="hidden-sm-up" />
					<div class="col-sm-6 col-lg-3">
						<div class="card">
							<div class="card-block">
								<h4 class="card-title">Forum</h4>
							</div>
							<a href="https://zzzprojects.uservoice.com/forums/327759-eval-expression-net" target="_blank"><i class="fa fa-weixin fa-5x"></i></a>
							<div class="card-block">
								<p class="card-text">Visit the forum to propose new features or to discuss about the library.</p>
								<a href="https://zzzprojects.uservoice.com/forums/327759-eval-expression-net" target="_blank">Forum</a>
							</div>
						</div>
					</div>
					<hr class="hidden-sm-up" />
					<div class="col-sm-6 col-lg-3">
						<div class="card">
							<div class="card-block">
								<h4 class="card-title">Open Source</h4>
							</div>
							<a href="https://github.com/zzzprojects/Eval-Expression.NET" target="_blank"><i class="fa fa-github fa-5x"></i></a>
							<div class="card-block">
								<p class="card-text">Access the source of the library you're using to understand better its logic.</p>
								<a href="https://github.com/zzzprojects/Eval-Expression.NET" target="_blank">GitHub</a>
							</div>
						</div>
					</div>
				</div>
			</div>
		</div>
		
		
		<!-- other product !-->
		<div id="product">
			<div class="container">
				<div class="row">
					<div class="col-lg-3">
						<h3>Bulk Operations</h3>
						<ul>
							<li><a href="http://www.zzzprojects.com/products/dotnet-development/entity-framework-extensions/" target="_blank">.NET Entity Framework Plus</a></li>
							<li><a href="http://www.zzzprojects.com/products/dotnet-development/bulk-operations/" target="_blank">.NET Bulk Operations</a></li>
						</ul>
					</div>
					<div class="col-lg-3">
						<h3>Expression Evaluator</h3>
						<ul>
							<li><a href="http://eval-expression.net/" target="_blank">Eval Expression.NET</a></li>
							<li><a href="http://eval-sql.net/" target="_blank">Eval SQL.NET</a></li>
						</ul>
					</div>
					<div class="col-lg-3">
						<h3>Others</h3>
						<ul>
							<li><a href="http://www.zzzprojects.com/products/dotnet-development/extension-methods/" target="_blank">Extension Methods</a></li>
							<li><a href="http://compiler-expression.net/" target="_blank">Compiler Expression.NET</a></li>
						</ul>
					</div>
				</div>
			</div>		
		</div>
		
		<!-- footer !-->
		<footer>
			<div class="container text-center-md-down">
				<div class="row">
					<div class="col-lg-6">
						Copyright © 2015 <a href="http://www.zzzprojects.com/" target="_blank" class="text-bold">ZZZ Projects Inc.</a>
						<div class="hidden-lg-up"></div>
						All rights reserved
					</div>
					<hr class="hidden-lg-up" />
					<div class="col-lg-6 text-right-lg-up social">
						<a href="https://www.facebook.com/zzzprojects" target="_blank"><i class="fa fa-facebook"></i></a>
						<a href="https://twitter.com/zzzprojects" target="_blank"><i class="fa fa-twitter"></i></a>
						<a href="https://plus.google.com/+Zzzprojects_NetSQL/posts" target="_blank"><i class="fa fa-google-plus"></i></a>
						<a href="http://zzzprojects.us9.list-manage.com/subscribe?u=cecbc4775cf67bf1ff82018af&id=4765ffa5f8" target="_blank"><i class="fa fa-newspaper-o"></i></a>
					</div>
				</div>
			</div>
		</footer>

    <script type="text/javascript" src="https://ajax.googleapis.com/ajax/libs/jquery/2.1.4/jquery.min.js"></script>
    <script type="text/javascript" src="https://cdn.rawgit.com/twbs/bootstrap/v4-dev/dist/js/bootstrap.min.js"></script>
	<script type="text/javascript">
	  (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
	  (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
	  m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
	  })(window,document,'script','//www.google-analytics.com/analytics.js','ga');

	  ga('create', 'UA-55584370-3', 'auto');
	  ga('send', 'pageview');
	  
	  function purchase_validate() {
		if($("#agree_agreement").prop('checked')) {
			return true;
		}
		
		$("#error_validation").modal('show')
		return false;
	  }
	</script>
  </body>
</html>

<style>
/* general */
* {
	 font-family: "Bitter",Georgia,"Times New Roman",serif;
}
.highlight * {
	font-family: Consolas, "Liberation Mono", Menlo, Courier, monospace;
}
.text-bold {
	font-weight: 700;
}
.text-green {
	color: rgb(68, 157, 68);
}
@media (max-width: 61em) {
	.text-center-md-down {
		text-align: center;
	}
}
@media (max-width: 33em) {
	.text-center-xs-down {
		text-align: center;
	}
}
@media (min-width: 62em) {
	.text-right-lg-up {
		text-align: right;
	}
}

/* section general */
#top-header {
	background-color: #111;
	border-bottom: 1px solid #000;
	font-size: 14px;
	padding: 5px 0px;
}
header {
	background: -moz-linear-gradient(top, #222, #333);
    background: -webkit-linear-gradient(top, #222, #333);
    background: -ms-linear-gradient(top, #222, #333);
    background: -o-linear-gradient(top, #222, #333);
    background: linear-gradient(top, #222, #333);
	border-bottom: 1px solid #111;
	border-top: 1px solid #333;
	padding: 40px 0px;
}
#feature {
    background: -moz-linear-gradient(top, #ddd, #f2f2f2);
    background: -webkit-linear-gradient(top, #ddd, #f2f2f2);
    background: -ms-linear-gradient(top, #ddd, #f2f2f2);
    background: -o-linear-gradient(top, #ddd, #f2f2f2);
    background: linear-gradient(top, #ddd, #f2f2f2);
	border-bottom: 1px solid #ddd;
    border-top: 1px solid #eee;
	padding-bottom: 60px;
}
#pricing {
	background-color: #fefefe;
	padding-top: 60px;
	padding-bottom: 60px;
}
#support {
	background: -moz-linear-gradient(top, #eee, #bbb);
    background: -webkit-linear-gradient(top, #eee, #bbb);
    background: -ms-linear-gradient(top, #eee, #bbb);
    background: -o-linear-gradient(top, #eee, #bbb);
    background: linear-gradient(top, #eee, #bbb);
	padding-top: 60px;
	padding-bottom: 60px;
	border-bottom: 1px solid #aaa;
	border-top: 1px solid #ccc;
}
#product {
    background: -moz-linear-gradient(top, #111, #222);
    background: -webkit-linear-gradient(top, #111, #222);
    background: -ms-linear-gradient(top, #111, #222);
    background: -o-linear-gradient(top, #111, #222);
    background: linear-gradient(top, #111, #222);
	border-bottom: 1px solid #111;
	border-top: 1px solid #333;
	color: #fefefe;
	padding: 20px 0px;
}
footer {
	background: -moz-linear-gradient(top, #333, #222);
    background: -webkit-linear-gradient(top, #333, #222);
    background: -ms-linear-gradient(top, #333, #222);
    background: -o-linear-gradient(top, #333, #222);
    background: linear-gradient(top, #333, #222);
	border-top: 1px solid #444;
	color: #666;
	padding-top: 5px;
	padding-bottom: 5px;
}

/* top-header */
#top-header a {
	color: #fefefe;
	padding-left: 10px;
	padding-right: 10px;
	text-decoration: none;
} 
#top-header a:hover {
	opacity: 0.7;
    transition: all 0.4s ease-in-out 0s;
}

/* header */
header .card {
	background-color: transparent;
	border: none;
	color: #f1f1f1;
}
header .card h1 {
	font-size: 3.0rem;
}
header .card h3 {
	font-size: 1.3rem;
}
header .card hr {
	border-color: initial;
}
header .card .lead .btn {
	width: 175px;
}
header .card .lead .btn-left {
	margin-right: 20px;
}
header .card .lead .btn span {
	display: inline-block;
	height: 40px;
}
header .card .lead .btn span span {
	vertical-align : middle;
}
header .card .lead .text-muted {
	font-size: 14px;
	padding-top: 10px;
}
header .card .card-code {
	background-color: #f1f1f1;
	border: 2px solid #444;
	color: #000;
	min-height: 350px;
}
header .card .card-code {
	padding: 0px;
}
header .card .card-code .highlight,
header .card .card-code .highlight pre {
	background-color: transparent;
	border: none;
}
@media (max-width: 33em) {
	header .card h1 {
		font-size: 2.5rem;
	}
	header .card .lead .btn {
		margin-bottom: 20px;
	}
}

/* feature */
#feature h2 {
	font-size: 42px;
	letter-spacing: 4px;
	padding-top: 60px;
	text-align: center;
}
#feature h3 {
	letter-spacing: 1px;
	font-size: 16px;
	text-decoration: underline;
}
#feature .btn {
	margin-top: 40px;
}
@media (min-width: 62em) {
	#feature .row .col-lg-6:first-child {
		padding-right: 45px;
	}
	#feature .row .col-lg-6:last-child {
		padding-left: 45px;
	}
}

/* pricing */
#pricing h2 {
	margin-bottom: -10px;
}
#pricing .table thead th {
	text-align: center;
}
#pricing .table td {
	text-align: center;
}
#pricing .fa-times {
	color: #c9302c;
}
#pricing .fa-check-square-o {
	color: #449D44;
}

/* support */
#support {
	text-align: center;
}
#support h2 {
	padding-bottom: 20px;
}
#support h3 {
	font-size: 20px;
	padding-bottom: 40px;
}
#support .card {
	border: 0.0625rem solid #ccc;
}
#support .card-text {
	min-height: 75px;
}
#support i {
	color: #0275d8;
	padding-bottom: 20px;
}

/* product */
#product h3 {
	letter-spacing: 1px;
	font-size: 18px;
	font-weight: 700;
}
#product ul {
	list-style: none;
	padding-left: 0px;
}
#product ul li {
	padding-top: 5px;
}
#product a {
	color: #999;
	font-size: 14px;
	letter-spacing: 1px;
}
#product a:hover {
	color: #fefefe;
	opacity: 0.9;
	text-decoration: none;
    transition: all 0.4s ease-in-out 0s;
}

/* footer */
@media (max-width: 61em) {
  footer {
	padding: 20px 0;
  }
}
footer hr {
	border-color: #666;
	margin: 20px;
}
footer a {
	color: #666;
}
footer a:hover {
	color: #666;
	opacity: 0.7;
	text-decoration: none;
    transition: all 0.4s ease-in-out 0s;
}
footer .social a {
	font-size: 24px;
	padding: 0px 10px;
}
</style>
