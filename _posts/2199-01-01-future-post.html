---
title: 'Blog Post number 1'
date: 2012-08-14
permalink: /posts/2012/08/blog-post-1/
tags:
  - cool posts
  - category1
  - category2
---

<!doctype html>
<html class="no-js" lang="en">
  <head><meta charset="utf-8"/>
    <meta name="viewport" content="width=device-width,initial-scale=1"/>
    <meta name="color-scheme" content="light dark"><meta name="generator" content="Docutils 0.19: https://docutils.sourceforge.io/" />
<link rel="index" title="Index" href="../genindex.html" /><link rel="search" title="Search" href="../search.html" /><link rel="next" title="Constrained Policy Optimization" href="../saferl/cpo.html" /><link rel="prev" title="Trust Region Policy Optimization" href="trpo.html" />

    <!-- Generated with Sphinx 6.2.1 and Furo 2023.03.27 -->
        <title>Proximal Policy Optimization - </title>
      <link rel="stylesheet" type="text/css" href="../_static/pygments.css" />
    <link rel="stylesheet" type="text/css" href="../_static/styles/furo.css?digest=fad236701ea90a88636c2a8c73b44ae642ed2a53" />
    <link rel="stylesheet" type="text/css" href="../_static/copybutton.css" />
    <link rel="stylesheet" type="text/css" href="../_static/design-style.1e8bd061cd6da7fc9cf755528e8ffc24.min.css" />
    <link rel="stylesheet" type="text/css" href="../_static/styles/furo-extensions.css?digest=30d1aed668e5c3a91c3e3bf6a60b675221979f0e" />
    
    


<style>
  body {
    --color-code-background: #f8f8f8;
  --color-code-foreground: black;
  --color-brand-primary: #4E98C8;
  --color-brand-content: #67A4BA;
  --sd-color-success: #5EA69C;
  --sd-color-info: #76A2DB;
  --sd-color-warning: #AD677E;
  
  }
  @media not print {
    body[data-theme="dark"] {
      --color-code-background: #272822;
  --color-code-foreground: #f8f8f2;
  
    }
    @media (prefers-color-scheme: dark) {
      body:not([data-theme="light"]) {
        --color-code-background: #272822;
  --color-code-foreground: #f8f8f2;
  
      }
    }
  }
</style></head>
  <body>
    
    <script>
      document.body.dataset.theme = localStorage.getItem("theme") || "auto";
    </script>
    

<svg xmlns="http://www.w3.org/2000/svg" style="display: none;">
  <symbol id="svg-toc" viewBox="0 0 24 24">
    <title>Contents</title>
    <svg stroke="currentColor" fill="currentColor" stroke-width="0" viewBox="0 0 1024 1024">
      <path d="M408 442h480c4.4 0 8-3.6 8-8v-56c0-4.4-3.6-8-8-8H408c-4.4 0-8 3.6-8 8v56c0 4.4 3.6 8 8 8zm-8 204c0 4.4 3.6 8 8 8h480c4.4 0 8-3.6 8-8v-56c0-4.4-3.6-8-8-8H408c-4.4 0-8 3.6-8 8v56zm504-486H120c-4.4 0-8 3.6-8 8v56c0 4.4 3.6 8 8 8h784c4.4 0 8-3.6 8-8v-56c0-4.4-3.6-8-8-8zm0 632H120c-4.4 0-8 3.6-8 8v56c0 4.4 3.6 8 8 8h784c4.4 0 8-3.6 8-8v-56c0-4.4-3.6-8-8-8zM115.4 518.9L271.7 642c5.8 4.6 14.4.5 14.4-6.9V388.9c0-7.4-8.5-11.5-14.4-6.9L115.4 505.1a8.74 8.74 0 0 0 0 13.8z"/>
    </svg>
  </symbol>
  <symbol id="svg-menu" viewBox="0 0 24 24">
    <title>Menu</title>
    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor"
      stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="feather-menu">
      <line x1="3" y1="12" x2="21" y2="12"></line>
      <line x1="3" y1="6" x2="21" y2="6"></line>
      <line x1="3" y1="18" x2="21" y2="18"></line>
    </svg>
  </symbol>
  <symbol id="svg-arrow-right" viewBox="0 0 24 24">
    <title>Expand</title>
    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor"
      stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="feather-chevron-right">
      <polyline points="9 18 15 12 9 6"></polyline>
    </svg>
  </symbol>
  <symbol id="svg-sun" viewBox="0 0 24 24">
    <title>Light mode</title>
    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor"
      stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" class="feather-sun">
      <circle cx="12" cy="12" r="5"></circle>
      <line x1="12" y1="1" x2="12" y2="3"></line>
      <line x1="12" y1="21" x2="12" y2="23"></line>
      <line x1="4.22" y1="4.22" x2="5.64" y2="5.64"></line>
      <line x1="18.36" y1="18.36" x2="19.78" y2="19.78"></line>
      <line x1="1" y1="12" x2="3" y2="12"></line>
      <line x1="21" y1="12" x2="23" y2="12"></line>
      <line x1="4.22" y1="19.78" x2="5.64" y2="18.36"></line>
      <line x1="18.36" y1="5.64" x2="19.78" y2="4.22"></line>
    </svg>
  </symbol>
  <symbol id="svg-moon" viewBox="0 0 24 24">
    <title>Dark mode</title>
    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor"
      stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" class="icon-tabler-moon">
      <path stroke="none" d="M0 0h24v24H0z" fill="none" />
      <path d="M12 3c.132 0 .263 0 .393 0a7.5 7.5 0 0 0 7.92 12.446a9 9 0 1 1 -8.313 -12.454z" />
    </svg>
  </symbol>
  <symbol id="svg-sun-half" viewBox="0 0 24 24">
    <title>Auto light/dark mode</title>
    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor"
      stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" class="icon-tabler-shadow">
      <path stroke="none" d="M0 0h24v24H0z" fill="none"/>
      <circle cx="12" cy="12" r="9" />
      <path d="M13 12h5" />
      <path d="M13 15h4" />
      <path d="M13 18h1" />
      <path d="M13 9h4" />
      <path d="M13 6h1" />
    </svg>
  </symbol>
</svg>

<input type="checkbox" class="sidebar-toggle" name="__navigation" id="__navigation">
<input type="checkbox" class="sidebar-toggle" name="__toc" id="__toc">
<label class="overlay sidebar-overlay" for="__navigation">
  <div class="visually-hidden">Hide navigation sidebar</div>
</label>
<label class="overlay toc-overlay" for="__toc">
  <div class="visually-hidden">Hide table of contents sidebar</div>
</label>



<div class="page">
  <header class="mobile-header">
    <div class="header-left">
      <label class="nav-overlay-icon" for="__navigation">
        <div class="visually-hidden">Toggle site navigation sidebar</div>
        <i class="icon"><svg><use href="#svg-menu"></use></svg></i>
      </label>
    </div>
    <div class="header-center">
      <a href="../index.html"><div class="brand"> </div></a>
    </div>
    <div class="header-right">
      <div class="theme-toggle-container theme-toggle-header">
        <button class="theme-toggle">
          <div class="visually-hidden">Toggle Light / Dark / Auto color theme</div>
          <svg class="theme-icon-when-auto"><use href="#svg-sun-half"></use></svg>
          <svg class="theme-icon-when-dark"><use href="#svg-moon"></use></svg>
          <svg class="theme-icon-when-light"><use href="#svg-sun"></use></svg>
        </button>
      </div>
      <label class="toc-overlay-icon toc-header-icon" for="__toc">
        <div class="visually-hidden">Toggle table of contents sidebar</div>
        <i class="icon"><svg><use href="#svg-toc"></use></svg></i>
      </label>
    </div>
  </header>
  <aside class="sidebar-drawer">
    <div class="sidebar-container">
      
      <div class="sidebar-sticky"><a class="sidebar-brand" href="../index.html">
  
  <div class="sidebar-logo-container">
    <img class="sidebar-logo" src="../_static/logo.png" alt="Logo"/>
  </div>
  
  <span class="sidebar-brand-text"> </span>
  
</a><form class="sidebar-search-container" method="get" action="../search.html" role="search">
  <input class="sidebar-search" placeholder="Search" name="q" aria-label="Search">
  <input type="hidden" name="check_keywords" value="yes">
  <input type="hidden" name="area" value="default">
</form>
<div id="searchbox"></div><div class="sidebar-scroll"><div class="sidebar-tree">
  <p class="caption" role="heading"><span class="caption-text">get started</span></p>
<ul>
<li class="toctree-l1"><a class="reference internal" href="../start/installation.html">Installation</a></li>
<li class="toctree-l1"><a class="reference internal" href="../start/usage.html">Usage Video</a></li>
</ul>
<p class="caption" role="heading"><span class="caption-text">mathematical theory</span></p>
<ul>
<li class="toctree-l1"><a class="reference internal" href="../foundations/notations.html">Mathematical Notations</a></li>
<li class="toctree-l1"><a class="reference internal" href="../foundations/vector.html">Vector and Martrix</a></li>
<li class="toctree-l1"><a class="reference internal" href="../foundations/lagrange.html">Lagrange Duality</a></li>
</ul>
<p class="caption" role="heading"><span class="caption-text">base rl algorithms</span></p>
<ul class="current">
<li class="toctree-l1"><a class="reference internal" href="trpo.html">Trust Region Policy Optimization</a></li>
<li class="toctree-l1 current current-page"><a class="current reference internal" href="#">Proximal Policy Optimization</a></li>
</ul>
<p class="caption" role="heading"><span class="caption-text">safe rl algorithms</span></p>
<ul>
<li class="toctree-l1"><a class="reference internal" href="../saferl/cpo.html">Constrained Policy Optimization</a></li>
<li class="toctree-l1"><a class="reference internal" href="../saferl/pcpo.html">Projection-Based Constrained Policy Optimization</a></li>
<li class="toctree-l1"><a class="reference internal" href="../saferl/focops.html">First Order Constrained Optimization in Policy Space</a></li>
<li class="toctree-l1"><a class="reference internal" href="../saferl/lag.html">Lagrangian Methods</a></li>
</ul>
<p class="caption" role="heading"><span class="caption-text">base rl algorithms api</span></p>
<ul>
<li class="toctree-l1"><a class="reference internal" href="../baserlapi/on_policy.html">Base On-policy Algorithms</a></li>
<li class="toctree-l1"><a class="reference internal" href="../baserlapi/off_policy.html">Base Off-policy Algorithms</a></li>
</ul>
<p class="caption" role="heading"><span class="caption-text">safe rl algorithms api</span></p>
<ul>
<li class="toctree-l1"><a class="reference internal" href="../saferlapi/first_order.html">First Order Algorithms</a></li>
<li class="toctree-l1"><a class="reference internal" href="../saferlapi/second_order.html">Second Order Algorithms</a></li>
<li class="toctree-l1"><a class="reference internal" href="../saferlapi/lagrange.html">Lagrange Algorithms</a></li>
<li class="toctree-l1"><a class="reference internal" href="../saferlapi/penalty_function.html">Penalty Function Algorithms</a></li>
</ul>
<p class="caption" role="heading"><span class="caption-text">common api</span></p>
<ul>
<li class="toctree-l1"><a class="reference internal" href="../common/buffer.html">OmniSafe Buffer</a></li>
<li class="toctree-l1"><a class="reference internal" href="../common/exp_grid.html">OmniSafe Experiment Grid</a></li>
<li class="toctree-l1"><a class="reference internal" href="../common/lagrange.html">OmniSafe Lagrange Multiplier</a></li>
<li class="toctree-l1"><a class="reference internal" href="../common/normalizer.html">OmniSafe Normalizer</a></li>
<li class="toctree-l1"><a class="reference internal" href="../common/logger.html">OmniSafe Logger</a></li>
<li class="toctree-l1"><a class="reference internal" href="../common/simmer_agent.html">OmniSafe Simmer Agent</a></li>
<li class="toctree-l1"><a class="reference internal" href="../common/stastics_tool.html">OmniSafe Statistics Tools</a></li>
</ul>
<p class="caption" role="heading"><span class="caption-text">utils api</span></p>
<ul>
<li class="toctree-l1"><a class="reference internal" href="../utils/config.html">OmniSafe Config</a></li>
<li class="toctree-l1"><a class="reference internal" href="../utils/distributed.html">OmniSafe Distributed</a></li>
<li class="toctree-l1"><a class="reference internal" href="../utils/math.html">OmniSafe Math</a></li>
<li class="toctree-l1"><a class="reference internal" href="../utils/model.html">OmniSafe Model Utils</a></li>
<li class="toctree-l1"><a class="reference internal" href="../utils/tools.html">OmniSafe Tools</a></li>
<li class="toctree-l1"><a class="reference internal" href="../utils/plotter.html">OmniSafe Plotter</a></li>
</ul>
<p class="caption" role="heading"><span class="caption-text">models api</span></p>
<ul>
<li class="toctree-l1"><a class="reference internal" href="../model/actor.html">OmniSafe Actor</a></li>
<li class="toctree-l1"><a class="reference internal" href="../model/critic.html">OmniSafe Critic</a></li>
<li class="toctree-l1"><a class="reference internal" href="../model/actor_critic.html">OmniSafe Actor Critic</a></li>
</ul>
<p class="caption" role="heading"><span class="caption-text">envs api</span></p>
<ul>
<li class="toctree-l1"><a class="reference internal" href="../envs/core.html">OmniSafe Core Environment</a></li>
<li class="toctree-l1"><a class="reference internal" href="../envs/wrapper.html">OmniSafe Wrapper</a></li>
<li class="toctree-l1"><a class="reference internal" href="../envs/safety_gymnasium.html">Safety Gymnasium Environment</a></li>
<li class="toctree-l1"><a class="reference internal" href="../envs/adapter.html">OmniSafe Adapter</a></li>
</ul>

</div>
</div>

      </div>
      
    </div>
  </aside>
  <div class="main">
    <div class="content">
      <div class="article-container">
        <a href="#" class="back-to-top muted-link">
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24">
            <path d="M13 20h-2V8l-5.5 5.5-1.42-1.42L12 4.16l7.92 7.92-1.42 1.42L13 8v12z"></path>
          </svg>
          <span>Back to top</span>
        </a>
        <div class="content-icon-container">
          
<div class="theme-toggle-container theme-toggle-content">
            <button class="theme-toggle">
              <div class="visually-hidden">Toggle Light / Dark / Auto color theme</div>
              <svg class="theme-icon-when-auto"><use href="#svg-sun-half"></use></svg>
              <svg class="theme-icon-when-dark"><use href="#svg-moon"></use></svg>
              <svg class="theme-icon-when-light"><use href="#svg-sun"></use></svg>
            </button>
          </div>
          <label class="toc-overlay-icon toc-content-icon" for="__toc">
            <div class="visually-hidden">Toggle table of contents sidebar</div>
            <i class="icon"><svg><use href="#svg-toc"></use></svg></i>
          </label>
        </div>
        <article role="main">
          <section id="proximal-policy-optimization">
<h1>Proximal Policy Optimization<a class="headerlink" href="#proximal-policy-optimization" title="Permalink to this heading">#</a></h1>
<section id="quick-facts">
<h2>Quick Facts<a class="headerlink" href="#quick-facts" title="Permalink to this heading">#</a></h2>
<div class="sd-card sd-sphinx-override sd-mb-3 sd-shadow-sm sd-outline-info sd-rounded-1 docutils">
<div class="sd-card-body sd-font-weight-bold docutils">
<ol class="arabic simple">
<li><p class="sd-card-text">PPO is an <span class="sd-sphinx-override sd-badge sd-outline-info sd-text-info">on-policy</span> algorithm.</p></li>
<li><p class="sd-card-text">PPO can be used for environments with both <span class="sd-sphinx-override sd-badge sd-outline-info sd-text-info">discrete</span> and <span class="sd-sphinx-override sd-badge sd-outline-info sd-text-info">continuous</span> action spaces.</p></li>
<li><p class="sd-card-text">PPO can be thought of as being a simple implementation of <a class="sd-sphinx-override sd-badge sd-outline-info sd-text-info reference internal" href="trpo.html"><span class="doc">TRPO</span></a>  .</p></li>
<li><p class="sd-card-text">The OmniSafe implementation of PPO support <span class="sd-sphinx-override sd-badge sd-outline-info sd-text-info">parallelization</span>.</p></li>
<li><p class="sd-card-text">An <a class="sd-sphinx-override sd-badge sd-outline-info sd-text-info reference internal" href="../baserlapi/on_policy.html#ppoapi"><span class="std std-ref">API Documentation</span></a> is available for PPO.</p></li>
</ol>
</div>
</div>
</section>
<section id="ppo-theorem">
<h2>PPO Theorem<a class="headerlink" href="#ppo-theorem" title="Permalink to this heading">#</a></h2>
<section id="background">
<h3>Background<a class="headerlink" href="#background" title="Permalink to this heading">#</a></h3>
<p><strong>Proximal Policy Optimization(PPO)</strong> is a reinforcement learning algorithm inheriting some of the
benefits of <a class="reference internal" href="trpo.html"><span class="doc">TRPO</span></a>,
However, it is much simpler to implement.
PPO shares the same goal as TRPO:</p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>How can we take the largest possible improvement step on a policy update
using the available data, without stepping too far and causing performance
collapse?</p>
</div>
<p>However, instead of using a complex second-order method like TRPO, PPO uses a
few tricks to keep the new policies close to the old ones. There are two
primary variants of PPO:
<a class="sd-sphinx-override sd-badge sd-outline-info sd-text-info reference internal" href="#ppo-penalty"><span class="std std-ref">PPO-Penalty</span></a> and
<a class="sd-sphinx-override sd-badge sd-outline-info sd-text-info reference internal" href="#ppo-clip"><span class="std std-ref">PPO-Clip</span></a>.</p>
<div class="sd-container-fluid sd-sphinx-override sd-mb-4 docutils">
<div class="sd-row sd-row-cols-2 sd-row-cols-xs-2 sd-row-cols-sm-2 sd-row-cols-md-2 sd-row-cols-lg-2 docutils">
<div class="sd-col sd-d-flex-column sd-col-12 sd-col-xs-12 sd-col-sm-6 sd-col-md-6 sd-col-lg-5 docutils">
<div class="sd-card sd-sphinx-override sd-mb-3 sd-shadow-sm sd-outline-warning sd-rounded-1 sd-font-weight-bold docutils">
<div class="sd-card-header sd-bg-warning sd-text-white sd-font-weight-bold docutils">
<p class="sd-card-text">Problems of TRPO</p>
</div>
<div class="sd-card-body docutils">
<ul class="simple">
<li><p class="sd-card-text">The calculation of KL divergence in TRPO is too complicated.</p></li>
<li><p class="sd-card-text">Only the raw data sampled by the Monte Carlo method is used.</p></li>
<li><p class="sd-card-text">Using second-order optimization methods.</p></li>
</ul>
</div>
</div>
</div>
<div class="sd-col sd-d-flex-column sd-col-12 sd-col-xs-12 sd-col-sm-6 sd-col-md-6 sd-col-lg-6 docutils">
<div class="sd-card sd-sphinx-override sd-mb-3 sd-shadow-sm sd-outline-primary sd-rounded-1 sd-font-weight-bold docutils">
<div class="sd-card-header sd-bg-primary sd-text-white sd-font-weight-bold docutils">
<p class="sd-card-text">Advantage of PPO</p>
</div>
<div class="sd-card-body docutils">
<ul class="simple">
<li><p class="sd-card-text">Using <code class="docutils literal notranslate"><span class="pre">clip</span></code> method to make the difference between the two strategies less significant.</p></li>
<li><p class="sd-card-text">Using the <span class="math notranslate nohighlight">\(\text{GAE}\)</span> method to process data.</p></li>
<li><p class="sd-card-text">Simple to implement.</p></li>
<li><p class="sd-card-text">Using first-order optimization methods.</p></li>
</ul>
</div>
</div>
</div>
</div>
</div>
</section>
<hr class="docutils" />
<section id="optimization-objective">
<h3>Optimization Objective<a class="headerlink" href="#optimization-objective" title="Permalink to this heading">#</a></h3>
<p>In the previous chapters, we introduced that TRPO solves the following
optimization problems:</p>
<div class="math-wrapper docutils container" id="equation-ppo-eq-1">
<span id="ppo-eq-1"></span><div class="math notranslate nohighlight" id="equation-ppo-eq-1">
<span id="ppo-eq-1"></span><span class="eqno">(1)<a class="headerlink" href="#equation-ppo-eq-1" title="Permalink to this equation">#</a></span>\[\begin{split}&amp; \pi_{k+1}=\arg\max_{\pi \in \Pi_{\boldsymbol{\theta}}}J^R(\pi)\\
\text{s.t.}\quad &amp; D(\pi,\pi_k)\le\delta\end{split}\]</div>
</div>
<p>where <span class="math notranslate nohighlight">\(\Pi_{\boldsymbol{\theta}} \subseteq \Pi\)</span> denotes the set of
parameterized policies with parameters <span class="math notranslate nohighlight">\(\boldsymbol{\theta}\)</span>, and
<span class="math notranslate nohighlight">\(D\)</span> is some distance measure.</p>
<p>TRPO tackles the challenge of determining the appropriate direction and step size for actor updates, aiming to improve performance while minimizing deviations from the original actor. To achieve this, TRPO reformulates
Problem <a class="reference internal" href="#equation-ppo-eq-1">Eq.1</a> as:</p>
<div class="math-wrapper docutils container" id="equation-ppo-eq-2">
<span id="ppo-eq-2"></span><div class="math notranslate nohighlight" id="equation-ppo-eq-2">
<span id="ppo-eq-2"></span><span class="eqno">(2)<a class="headerlink" href="#equation-ppo-eq-2" title="Permalink to this equation">#</a></span>\[\begin{split}\underset{\theta}{\max} \quad &amp; L_{\theta_{old}}(\theta)  \\
\text{s.t. } \quad &amp; \bar{D}_{\mathrm{KL}}(\theta_{old}, \theta) \le \delta\end{split}\]</div>
</div>
<p>where
<span class="math notranslate nohighlight">\(L_{\theta_{old}}(\theta)= \frac{\pi_\theta(a \mid s)}{\pi_{\theta_{old}}(a \mid s)} \hat{A}_\pi(s, a)\)</span>,
Moreover, <span class="math notranslate nohighlight">\(\hat{A}_{\pi}(s, a)\)</span> is an estimator of the advantage function
given <span class="math notranslate nohighlight">\(s\)</span> and  <span class="math notranslate nohighlight">\(a\)</span>.</p>
<p>You may still have a question: Why are we using <span class="math notranslate nohighlight">\(\hat{A}\)</span> instead of
<span class="math notranslate nohighlight">\(A\)</span>.
This is a trick named <strong>generalized advantage estimator</strong> (<span class="math notranslate nohighlight">\(\text{GAE}\)</span>).
Almost all advanced reinforcement learning algorithms use <span class="math notranslate nohighlight">\(\text{GAE}\)</span>
technique to estimate more efficient advantage <span class="math notranslate nohighlight">\(A\)</span>.
<span class="math notranslate nohighlight">\(\hat{A}\)</span> is the <span class="math notranslate nohighlight">\(\text{GAE}\)</span> version of <span class="math notranslate nohighlight">\(A\)</span>.</p>
<hr class="docutils" />
</section>
<section id="ppo-penalty">
<span id="id1"></span><h3>PPO-Penalty<a class="headerlink" href="#ppo-penalty" title="Permalink to this heading">#</a></h3>
<p>TRPO suggests using a penalty instead of a constraint to solve the
unconstrained optimization problem:</p>
<div class="math-wrapper docutils container" id="equation-ppo-eq-3">
<span id="ppo-eq-3"></span><div class="math notranslate nohighlight" id="equation-ppo-eq-3">
<span id="ppo-eq-3"></span><span class="eqno">(3)<a class="headerlink" href="#equation-ppo-eq-3" title="Permalink to this equation">#</a></span>\[\max _\theta \mathbb{E}[\frac{\pi_\theta(a \mid s)}{\pi_{\theta_{old}}(a \mid s)} \hat{A}_\pi(s, a)-\beta D_{K L}[\pi_{\theta_{old}}(* \mid s), \pi_\theta(* \mid s)]]\]</div>
</div>
<p>However, experiments have shown that simply choosing a fixed penalty
coefficient <span class="math notranslate nohighlight">\(\beta\)</span> and optimizing the penalized objective <a class="reference internal" href="#equation-ppo-eq-3">Eq.3</a>
with SGD (stochastic gradient descent) is not sufficient. Therefore, TRPO
abandoned this method.</p>
<p>PPO-Penalty uses an approach called <code class="docutils literal notranslate"><span class="pre">Adaptive</span> <span class="pre">KL</span> <span class="pre">Penalty</span> <span class="pre">Coefficient</span></code> to
address this problem and improve the performance of <a class="reference internal" href="#equation-ppo-eq-3">Eq.3</a> in
experiments. In the simplest implementation of this algorithm, PPO-Penalty
performs the following steps in each policy update iteration:</p>
<div class="sd-container-fluid sd-sphinx-override sd-mb-4 docutils">
<div class="sd-row sd-row-cols-2 sd-row-cols-xs-2 sd-row-cols-sm-2 sd-row-cols-md-2 sd-row-cols-lg-2 docutils">
<div class="sd-col sd-d-flex-column sd-col-12 sd-col-xs-12 sd-col-sm-6 sd-col-md-6 sd-col-lg-7 docutils">
<div class="sd-card sd-sphinx-override sd-mb-3 sd-shadow-sm sd-outline-info sd-rounded-1 sd-font-weight-bold docutils">
<div class="sd-card-header sd-bg-info sd-text-white sd-font-weight-bold docutils">
<p class="sd-card-text">Step I</p>
</div>
<div class="sd-card-body docutils">
<p class="sd-card-text">Using several epochs of mini-batch SGD, optimize the KL-penalized objective shown as <a class="reference internal" href="#equation-ppo-eq-3">Eq.3</a>,</p>
<div class="math-wrapper docutils container" id="equation-ppo-eq-4">
<div class="math notranslate nohighlight" id="equation-ppo-eq-4">
<span class="eqno">(4)<a class="headerlink" href="#equation-ppo-eq-4" title="Permalink to this equation">#</a></span>\[\begin{split}L^{\mathrm{KLPEN}}(\theta)&amp;=\hat{\mathbb{E}}[\frac{\pi_\theta(a \mid s)}{\pi_{\theta_{old}}(a \mid s)} \hat{A}_\pi(s, a)\\
&amp;-\beta D_{K L}[\pi_{\theta_{old}}(* \mid s), \pi_\theta(* \mid s)]]\end{split}\]</div>
</div>
</div>
</div>
</div>
<div class="sd-col sd-d-flex-column sd-col-12 sd-col-xs-12 sd-col-sm-6 sd-col-md-6 sd-col-lg-5 docutils">
<div class="sd-card sd-sphinx-override sd-mb-3 sd-shadow-sm sd-outline-info sd-rounded-1 sd-font-weight-bold docutils">
<div class="sd-card-header sd-bg-info sd-text-white sd-font-weight-bold docutils">
<p class="sd-card-text">Step II</p>
</div>
<div class="sd-card-body docutils">
<p class="sd-card-text">Compute <span class="math notranslate nohighlight">\(d=\hat{\mathbb{E}}[\mathrm{KL}[\pi_{\theta_{\text {old }}}(\cdot \mid s), \pi_\theta(\cdot \mid s)]]\)</span></p>
<p class="sd-card-text">If <span class="math notranslate nohighlight">\(d&lt;d_{\text {targ }} / 1.5, \beta \leftarrow \beta / 2\)</span></p>
<p class="sd-card-text">If <span class="math notranslate nohighlight">\(d&gt;d_{\text {targ }} \times 1.5, \beta \leftarrow \beta * 2\)</span></p>
<p class="sd-card-text">The updated <span class="math notranslate nohighlight">\(\beta\)</span> is used for the next policy update.</p>
</div>
</div>
</div>
</div>
</div>
<hr class="docutils" />
</section>
<section id="ppo-clip">
<span id="id2"></span><h3>PPO-Clip<a class="headerlink" href="#ppo-clip" title="Permalink to this heading">#</a></h3>
<p>Let <span class="math notranslate nohighlight">\(r(\theta)\)</span> denote the probability ratio
<span class="math notranslate nohighlight">\(r(\theta)=\frac{\pi_\theta(a \mid s)}{\pi_{\theta_{old}}(a \mid s)}\)</span>,
PPO-Clip rewrite the surrogate objective as:</p>
<div class="math-wrapper docutils container" id="equation-ppo-eq-5">
<span id="ppo-eq-5"></span><div class="math notranslate nohighlight" id="equation-ppo-eq-5">
<span id="ppo-eq-5"></span><span class="eqno">(5)<a class="headerlink" href="#equation-ppo-eq-5" title="Permalink to this equation">#</a></span>\[L^{\mathrm{CLIP}}(\pi)=\mathbb{E}[\text{min} (r(\theta) \hat{A}_{\pi}(s, a), \text{clip}(r(\theta), 1-\varepsilon, 1+\varepsilon) \hat{A}_{\pi}(s, a))]\]</div>
</div>
<p>The hyperparameter <span class="math notranslate nohighlight">\(\varepsilon\)</span> represents a small value that approximately indicates the allowable distance between the new policy and the old policy. The formula involved in this context is quite intricate, making it challenging to comprehend its purpose or how it contributes to maintaining the proximity between the new and old policies. To facilitate a clearer understanding of the aforementioned expression,</p>
<p>let <span class="math notranslate nohighlight">\(L(s, a, \theta)\)</span> denote
<span class="math notranslate nohighlight">\(\max [r(\theta) \hat{A}_{\pi}(s, a), \text{clip}(r(\theta), 1-\varepsilon, 1+\varepsilon) \hat{A}_{\pi}(s, a)]\)</span>,
we’ll simplify the formula in two cases:</p>
<div class="sd-card sd-sphinx-override sd-mb-3 sd-shadow-sm sd-outline-info sd-rounded-1 sd-font-weight-bold docutils">
<div class="sd-card-header sd-bg-info sd-text-white sd-font-weight-bold docutils">
<p class="sd-card-text">PPO Clip</p>
</div>
<div class="sd-card-body docutils">
<ol class="arabic">
<li><p class="sd-card-text">When Advantage is positive, we can rewrite <span class="math notranslate nohighlight">\(L(s, a, \theta)\)</span> as:</p>
<div class="math-wrapper docutils container" id="equation-ppo-eq-6">
<div class="math notranslate nohighlight" id="equation-ppo-eq-6">
<span class="eqno">(6)<a class="headerlink" href="#equation-ppo-eq-6" title="Permalink to this equation">#</a></span>\[L(s, a, \theta)=\max (r(\theta),(1-\varepsilon)) \hat{A}_{\pi}(s, a)\]</div>
</div>
</li>
<li><p class="sd-card-text">When Advantage is negative, we can rewrite <span class="math notranslate nohighlight">\(L(s, a, \theta)\)</span> as:</p>
<div class="math-wrapper docutils container" id="equation-ppo-eq-7">
<div class="math notranslate nohighlight" id="equation-ppo-eq-7">
<span class="eqno">(7)<a class="headerlink" href="#equation-ppo-eq-7" title="Permalink to this equation">#</a></span>\[L(s, a, \theta)=\max (r(\theta),(1+\varepsilon)) \hat{A}_{\pi}(s, a)\]</div>
</div>
</li>
</ol>
</div>
</div>
<p>With the above clipped surrogate function and <a class="reference internal" href="#equation-ppo-eq-5">Eq.5</a>,
PPO-Clip can guarantee the new policy
would not update so far away from the old.
In the experiment, PPO-Clip performs better than PPO-Penalty.</p>
</section>
</section>
<hr class="docutils" />
<section id="practical-implementation">
<h2>Practical Implementation<a class="headerlink" href="#practical-implementation" title="Permalink to this heading">#</a></h2>
<section id="generalized-advantage-estimation">
<h3>Generalized Advantage Estimation<a class="headerlink" href="#generalized-advantage-estimation" title="Permalink to this heading">#</a></h3>
<p>One style of policy gradient implementation, popularized in and well-suited for
use with recurrent neural networks, runs the policy for <span class="math notranslate nohighlight">\(T\)</span>
timesteps (where <span class="math notranslate nohighlight">\(T\)</span> is much less than the episode length), and uses the
collected samples for an update. This style requires an advantage estimator
that does not look beyond timestep <span class="math notranslate nohighlight">\(T\)</span>. This section will focus on
producing an accurate estimate of the advantage function
<span class="math notranslate nohighlight">\(\hat{A}_{\pi}(s,a)\)</span> (Equals to <span class="math notranslate nohighlight">\(\hat{A}^{R}_{\pi}(s,a)\)</span> since only reward is considered here, same as the following.) using only information
from the current trajectory up to timestep <span class="math notranslate nohighlight">\(T\)</span>.</p>
<p>Define <span class="math notranslate nohighlight">\(\delta^V=r_t+\gamma V(s_{t+1})-V(s)\)</span> as the TD residual of
<span class="math notranslate nohighlight">\(V\)</span> with discount <span class="math notranslate nohighlight">\(\gamma\)</span>.
Next, let us consider taking the sum of <span class="math notranslate nohighlight">\(k\)</span> of these <span class="math notranslate nohighlight">\(\delta\)</span>
terms, which we will denote by <span class="math notranslate nohighlight">\(\hat{A}_{\pi}^{(k)}\)</span>.</p>
<div class="math-wrapper docutils container" id="equation-ppo-eq-8">
<div class="math notranslate nohighlight" id="equation-ppo-eq-8">
<span class="eqno">(8)<a class="headerlink" href="#equation-ppo-eq-8" title="Permalink to this equation">#</a></span>\[\begin{split}\begin{array}{ll}
\hat{A}_{\pi}^{(1)}:=\delta_t^V =-V(s_t)+r_t+\gamma V(s_{t+1}) \\
\hat{A}_{\pi}^{(2)}:=\delta_t^V+\gamma \delta_{t+1}^V =-V(s_t)+r_t+\gamma r_{t+1}+\gamma^2 V(s_{t+2}) \\
\hat{A}_{\pi}^{(3)}:=\delta_t^V+\gamma \delta_{t+1}^V+\gamma^2 \delta_{t+2}^V =-V(s_t)+r_t+\gamma r_{t+1}+\gamma^2 r_{t+2}+\gamma^3 V(s_{t+3}) \\
\hat{A}_{\pi}^{(k)}:=\sum_{l=0}^{k-1} \gamma^l \delta_{t+l}^V =-V(s_t)+r_t+\gamma r_{t+1}+\cdots+\gamma^{k-1} r_{t+k-1}+\gamma^k V(s_{t+k})
\end{array}\end{split}\]</div>
</div>
<p>We can consider <span class="math notranslate nohighlight">\(\hat{A}_{\pi}^{(k)}\)</span> to be an estimator of the advantage
function.</p>
<div class="admonition hint">
<p class="admonition-title">Hint</p>
<p>The bias generally becomes smaller as <span class="math notranslate nohighlight">\(k \rightarrow +\infty\)</span>,
since the term <span class="math notranslate nohighlight">\(\gamma^k V(s_{t+k})\)</span> becomes more heavily discounted.
Taking <span class="math notranslate nohighlight">\(k \rightarrow +\infty\)</span>, we get:</p>
<div class="math-wrapper docutils container" id="equation-ppo-eq-9">
<div class="math notranslate nohighlight" id="equation-ppo-eq-9">
<span class="eqno">(9)<a class="headerlink" href="#equation-ppo-eq-9" title="Permalink to this equation">#</a></span>\[\hat{A}_{\pi}^{(\infty)}=\sum_{l=0}^{\infty} \gamma^l \delta_{t+l}^V=-V(s_t)+\sum_{l=0}^{\infty} \gamma^l r_{t+l}\]</div>
</div>
<p>which is simply the empirical returns minus the value function baseline.</p>
</div>
<p>The generalized advantage estimator <span class="math notranslate nohighlight">\(\text{GAE}(\gamma,\lambda)\)</span> is
defined as the exponentially-weighted average of these <span class="math notranslate nohighlight">\(k\)</span>-step
estimators:</p>
<div class="math-wrapper docutils container" id="equation-ppo-eq-10">
<span id="ppo-eq-6"></span><div class="math notranslate nohighlight" id="equation-ppo-eq-10">
<span id="ppo-eq-6"></span><span class="eqno">(10)<a class="headerlink" href="#equation-ppo-eq-10" title="Permalink to this equation">#</a></span>\[\begin{split}\hat{A}_{\pi}:&amp;= (1-\lambda)(\hat{A}_{\pi}^{(1)}+\lambda \hat{A}_{\pi}^{(2)}+\lambda^2 \hat{A}_{\pi}^{(3)}+\ldots) \\
&amp;= (1-\lambda)(\delta_t^V+\lambda(\delta_t^V+\gamma \delta_{t+1}^V)+\lambda^2(\delta_t^V+\gamma \delta_{t+1}^V+\gamma^2 \delta_{t+2}^V)+\ldots) \\
&amp;= (1-\lambda)(\delta_t^V(1+\lambda+\lambda^2+\ldots)+\gamma \delta_{t+1}^V(\lambda+\lambda^2+\lambda^3+\ldots) .+\gamma^2 \delta_{t+2}^V(\lambda^2+\lambda^3+\lambda^4+\ldots)+\ldots) \\
&amp;= (1-\lambda)(\delta_t^V(\frac{1}{1-\lambda})+\gamma \delta_{t+1}^V(\frac{\lambda}{1-\lambda})+\gamma^2 \delta_{t+2}^V(\frac{\lambda^2}{1-\lambda})+\ldots) \\
&amp;= \sum_{l=0}^{\infty}(\gamma \lambda)^l \delta_{t+l}^V\end{split}\]</div>
</div>
<p>There are two notable special cases of this formula, obtained by setting
<span class="math notranslate nohighlight">\(\lambda =0\)</span> and <span class="math notranslate nohighlight">\(\lambda =1\)</span>.</p>
<div class="math-wrapper docutils container" id="equation-ppo-eq-11">
<div class="math notranslate nohighlight" id="equation-ppo-eq-11">
<span class="eqno">(11)<a class="headerlink" href="#equation-ppo-eq-11" title="Permalink to this equation">#</a></span>\[\begin{split}\text{GAE}(\gamma, 0):\quad &amp; \hat{A}_{\pi}:=\delta_t  =r_t+\gamma V(s_{t+1})-V(s_t) \\
\text{GAE}(\gamma, 1):\quad &amp; \hat{A}_{\pi}:=\sum_{l=0}^{\infty} \gamma^l \delta_{t+l}  =\sum_{l=0}^{\infty} \gamma^l r_{t+l}-V(s_t)\end{split}\]</div>
</div>
<div class="admonition hint">
<p class="admonition-title">Hint</p>
<p><span class="math notranslate nohighlight">\(\text{GAE}(\gamma,1)\)</span> is the traditional MC-based method to estimate the advantage function,
but it has a high variance due to the sum of terms.
<span class="math notranslate nohighlight">\(\text{GAE}(\gamma,0)\)</span> is TD-based method with low variance,
but it suffers from bias.</p>
</div>
<p>The generalized advantage estimator for <span class="math notranslate nohighlight">\(0\le\lambda\le1\)</span> makes a
compromise between bias and variance,
controlled by parameter <span class="math notranslate nohighlight">\(\lambda\)</span>.</p>
</section>
<section id="code-with-omnisafe">
<h3>Code with OmniSafe<a class="headerlink" href="#code-with-omnisafe" title="Permalink to this heading">#</a></h3>
<section id="quick-start">
<h4>Quick start<a class="headerlink" href="#quick-start" title="Permalink to this heading">#</a></h4>
<div class="sd-card sd-sphinx-override sd-mb-3 sd-shadow-sm sd-outline-success sd-rounded-1 sd-font-weight-bold docutils">
<div class="sd-card-header sd-bg-success sd-text-white sd-font-weight-bold docutils">
<p class="sd-card-text">Run PPO in OmniSafe</p>
</div>
<div class="sd-card-body docutils">
<p class="sd-card-text">Here are 3 ways to run PPO in OmniSafe:</p>
<ul class="simple">
<li><p class="sd-card-text">Run Agent from preset yaml file</p></li>
<li><p class="sd-card-text">Run Agent from custom config dict</p></li>
<li><p class="sd-card-text">Run Agent from custom terminal config</p></li>
</ul>
<div class="sd-tab-set docutils">
<input checked="checked" id="sd-tab-item-0" name="sd-tab-set-0" type="radio">
</input><label class="sd-tab-label" for="sd-tab-item-0">
Yaml file style</label><div class="sd-tab-content docutils">
<div class="highlight-python notranslate"><div class="highlight"><pre><span></span><span class="linenos">1</span><span class="kn">import</span> <span class="nn">omnisafe</span>
<span class="linenos">2</span>
<span class="linenos">3</span>
<span class="linenos">4</span><span class="n">env_id</span> <span class="o">=</span> <span class="s1">&#39;SafetyPointGoal1-v0&#39;</span>
<span class="linenos">5</span>
<span class="linenos">6</span><span class="n">agent</span> <span class="o">=</span> <span class="n">omnisafe</span><span class="o">.</span><span class="n">Agent</span><span class="p">(</span><span class="s1">&#39;PPO&#39;</span><span class="p">,</span> <span class="n">env_id</span><span class="p">)</span>
<span class="linenos">7</span><span class="n">agent</span><span class="o">.</span><span class="n">learn</span><span class="p">()</span>
</pre></div>
</div>
</div>
<input id="sd-tab-item-1" name="sd-tab-set-0" type="radio">
</input><label class="sd-tab-label" for="sd-tab-item-1">
Config dict style</label><div class="sd-tab-content docutils">
<div class="highlight-python notranslate"><div class="highlight"><pre><span></span><span class="linenos"> 1</span><span class="kn">import</span> <span class="nn">omnisafe</span>
<span class="linenos"> 2</span>
<span class="linenos"> 3</span>
<span class="linenos"> 4</span><span class="n">env_id</span> <span class="o">=</span> <span class="s1">&#39;SafetyPointGoal1-v0&#39;</span>
<span class="linenos"> 5</span><span class="n">custom_cfgs</span> <span class="o">=</span> <span class="p">{</span>
<span class="linenos"> 6</span>    <span class="s1">&#39;train_cfgs&#39;</span><span class="p">:</span> <span class="p">{</span>
<span class="linenos"> 7</span>        <span class="s1">&#39;total_steps&#39;</span><span class="p">:</span> <span class="mi">10000000</span><span class="p">,</span>
<span class="linenos"> 8</span>        <span class="s1">&#39;vector_env_nums&#39;</span><span class="p">:</span> <span class="mi">1</span><span class="p">,</span>
<span class="linenos"> 9</span>        <span class="s1">&#39;parallel&#39;</span><span class="p">:</span> <span class="mi">1</span><span class="p">,</span>
<span class="linenos">10</span>    <span class="p">},</span>
<span class="linenos">11</span>    <span class="s1">&#39;algo_cfgs&#39;</span><span class="p">:</span> <span class="p">{</span>
<span class="linenos">12</span>        <span class="s1">&#39;steps_per_epoch&#39;</span><span class="p">:</span> <span class="mi">20000</span><span class="p">,</span>
<span class="linenos">13</span>    <span class="p">},</span>
<span class="linenos">14</span>    <span class="s1">&#39;logger_cfgs&#39;</span><span class="p">:</span> <span class="p">{</span>
<span class="linenos">15</span>        <span class="s1">&#39;use_wandb&#39;</span><span class="p">:</span> <span class="kc">False</span><span class="p">,</span>
<span class="linenos">16</span>        <span class="s1">&#39;use_tensorboard&#39;</span><span class="p">:</span> <span class="kc">True</span><span class="p">,</span>
<span class="linenos">17</span>    <span class="p">},</span>
<span class="linenos">18</span><span class="p">}</span>
<span class="linenos">19</span>
<span class="linenos">20</span><span class="n">agent</span> <span class="o">=</span> <span class="n">omnisafe</span><span class="o">.</span><span class="n">Agent</span><span class="p">(</span><span class="s1">&#39;PPO&#39;</span><span class="p">,</span> <span class="n">env_id</span><span class="p">,</span> <span class="n">custom_cfgs</span><span class="o">=</span><span class="n">custom_cfgs</span><span class="p">)</span>
<span class="linenos">21</span><span class="n">agent</span><span class="o">.</span><span class="n">learn</span><span class="p">()</span>
</pre></div>
</div>
</div>
<input id="sd-tab-item-2" name="sd-tab-set-0" type="radio">
</input><label class="sd-tab-label" for="sd-tab-item-2">
Terminal config style</label><div class="sd-tab-content docutils">
<p class="sd-card-text">We use <code class="docutils literal notranslate"><span class="pre">train_policy.py</span></code> as the entrance file. You can train the agent with PPO simply using <code class="docutils literal notranslate"><span class="pre">train_policy.py</span></code>, with arguments about PPO and environments does the training.
For example, to run PPO in SafetyPointGoal1-v0 , with 1 torch thread, seed 0 and single environment, you can use the following command:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre><span></span><span class="linenos">1</span><span class="nb">cd</span><span class="w"> </span>examples
<span class="linenos">2</span>python<span class="w"> </span>train_policy.py<span class="w"> </span>--algo<span class="w"> </span>PPO<span class="w"> </span>--env-id<span class="w"> </span>SafetyPointGoal1-v0<span class="w"> </span>--parallel<span class="w"> </span><span class="m">1</span><span class="w"> </span>--total-steps<span class="w"> </span><span class="m">10000000</span><span class="w"> </span>--device<span class="w"> </span>cpu<span class="w"> </span>--vector-env-nums<span class="w"> </span><span class="m">1</span><span class="w"> </span>--torch-threads<span class="w"> </span><span class="m">1</span>
</pre></div>
</div>
</div>
</div>
</div>
</div>
<hr class="docutils" />
<p>Here is the documentation of PPO in PyTorch version.</p>
</section>
<section id="architecture-of-functions">
<h4>Architecture of functions<a class="headerlink" href="#architecture-of-functions" title="Permalink to this heading">#</a></h4>
<ul class="simple">
<li><p><code class="docutils literal notranslate"><span class="pre">PPO.learn()</span></code></p>
<ul>
<li><p><code class="docutils literal notranslate"><span class="pre">PPO._env.rollout()</span></code></p></li>
<li><p><code class="docutils literal notranslate"><span class="pre">PPO._update()</span></code></p>
<ul>
<li><p><code class="docutils literal notranslate"><span class="pre">PPO._buf.get()</span></code></p></li>
<li><p><code class="docutils literal notranslate"><span class="pre">PPO.update_lagrange_multiplier(ep_costs)</span></code></p></li>
<li><p><code class="docutils literal notranslate"><span class="pre">PPO._update_actor()</span></code></p></li>
<li><p><code class="docutils literal notranslate"><span class="pre">PPO._update_reward_critic()</span></code></p></li>
</ul>
</li>
</ul>
</li>
</ul>
</section>
<hr class="docutils" />
<section id="documentation-of-algorithm-specific-functions">
<h4>Documentation of algorithm specific functions<a class="headerlink" href="#documentation-of-algorithm-specific-functions" title="Permalink to this heading">#</a></h4>
<div class="sd-tab-set docutils">
<input checked="checked" id="sd-tab-item-3" name="sd-tab-set-1" type="radio">
</input><label class="sd-tab-label" for="sd-tab-item-3">
ppo._loss_pi()</label><div class="sd-tab-content docutils">
<div class="sd-card sd-sphinx-override sd-mb-3 sd-shadow-sm sd-outline-success sd-rounded-1 sd-font-weight-bold docutils">
<div class="sd-card-header sd-bg-success sd-text-white sd-font-weight-bold docutils">
<p class="sd-card-text">ppo._loss_pi()</p>
</div>
<div class="sd-card-body docutils">
<p class="sd-card-text">Compute the loss of <code class="docutils literal notranslate"><span class="pre">actor</span></code>, flowing the next steps:</p>
<ol class="arabic simple">
<li><p class="sd-card-text">Get the policy importance sampling ratio.</p></li>
</ol>
<div class="highlight-python notranslate"><div class="highlight"><pre><span></span><span class="linenos">1</span><span class="n">distribution</span> <span class="o">=</span> <span class="bp">self</span><span class="o">.</span><span class="n">_actor_critic</span><span class="o">.</span><span class="n">actor</span><span class="p">(</span><span class="n">obs</span><span class="p">)</span>
<span class="linenos">2</span><span class="n">logp_</span> <span class="o">=</span> <span class="bp">self</span><span class="o">.</span><span class="n">_actor_critic</span><span class="o">.</span><span class="n">actor</span><span class="o">.</span><span class="n">log_prob</span><span class="p">(</span><span class="n">act</span><span class="p">)</span>
<span class="linenos">3</span><span class="n">std</span> <span class="o">=</span> <span class="bp">self</span><span class="o">.</span><span class="n">_actor_critic</span><span class="o">.</span><span class="n">actor</span><span class="o">.</span><span class="n">std</span>
<span class="linenos">4</span><span class="n">ratio</span> <span class="o">=</span> <span class="n">torch</span><span class="o">.</span><span class="n">exp</span><span class="p">(</span><span class="n">logp_</span> <span class="o">-</span> <span class="n">logp</span><span class="p">)</span>
</pre></div>
</div>
<ol class="arabic simple" start="2">
<li><p class="sd-card-text">Get the clipped surrogate function.</p></li>
</ol>
<div class="highlight-python notranslate"><div class="highlight"><pre><span></span><span class="linenos">1</span><span class="n">ratio_cliped</span> <span class="o">=</span> <span class="n">torch</span><span class="o">.</span><span class="n">clamp</span><span class="p">(</span>
<span class="linenos">2</span>    <span class="n">ratio</span><span class="p">,</span> <span class="mi">1</span> <span class="o">-</span> <span class="bp">self</span><span class="o">.</span><span class="n">_cfgs</span><span class="o">.</span><span class="n">algo_cfgs</span><span class="o">.</span><span class="n">clip</span><span class="p">,</span> <span class="mi">1</span> <span class="o">+</span> <span class="bp">self</span><span class="o">.</span><span class="n">_cfgs</span><span class="o">.</span><span class="n">algo_cfgs</span><span class="o">.</span><span class="n">clip</span>
<span class="linenos">3</span><span class="p">)</span>
<span class="linenos">4</span><span class="n">loss</span> <span class="o">=</span> <span class="o">-</span><span class="n">torch</span><span class="o">.</span><span class="n">min</span><span class="p">(</span><span class="n">ratio</span> <span class="o">*</span> <span class="n">adv</span><span class="p">,</span> <span class="n">ratio_cliped</span> <span class="o">*</span> <span class="n">adv</span><span class="p">)</span><span class="o">.</span><span class="n">mean</span><span class="p">()</span>
<span class="linenos">5</span><span class="n">loss</span> <span class="o">-=</span> <span class="bp">self</span><span class="o">.</span><span class="n">_cfgs</span><span class="o">.</span><span class="n">algo_cfgs</span><span class="o">.</span><span class="n">entropy_coef</span> <span class="o">*</span> <span class="n">distribution</span><span class="o">.</span><span class="n">entropy</span><span class="p">()</span><span class="o">.</span><span class="n">mean</span><span class="p">()</span>
</pre></div>
</div>
<ol class="arabic simple" start="3">
<li><p class="sd-card-text">Return the loss of <code class="docutils literal notranslate"><span class="pre">actor</span></code>.</p></li>
</ol>
</div>
</div>
</div>
</div>
</section>
<hr class="docutils" />
<section id="configs">
<h4>Configs<a class="headerlink" href="#configs" title="Permalink to this heading">#</a></h4>
<div class="sd-tab-set docutils">
<input checked="checked" id="sd-tab-item-4" name="sd-tab-set-2" type="radio">
</input><label class="sd-tab-label" for="sd-tab-item-4">
Train</label><div class="sd-tab-content docutils">
<div class="sd-card sd-sphinx-override sd-mb-3 sd-shadow-sm sd-outline-success sd-rounded-1 sd-font-weight-bold docutils">
<div class="sd-card-header sd-bg-success sd-text-white sd-font-weight-bold docutils">
<p class="sd-card-text">Train Configs</p>
</div>
<div class="sd-card-body docutils">
<ul class="simple">
<li><p class="sd-card-text">device (str): Device to use for training, options: <code class="docutils literal notranslate"><span class="pre">cpu</span></code>, <code class="docutils literal notranslate"><span class="pre">cuda</span></code>, <code class="docutils literal notranslate"><span class="pre">cuda:0</span></code>, etc.</p></li>
<li><p class="sd-card-text">torch_threads (int): Number of threads to use for PyTorch.</p></li>
<li><p class="sd-card-text">total_steps (int): Total number of steps to train the agent.</p></li>
<li><p class="sd-card-text">parallel (int): Number of parallel agents, similar to A3C.</p></li>
<li><p class="sd-card-text">vector_env_nums (int): Number of the vector environments.</p></li>
</ul>
</div>
</div>
</div>
<input id="sd-tab-item-5" name="sd-tab-set-2" type="radio">
</input><label class="sd-tab-label" for="sd-tab-item-5">
Algorithm</label><div class="sd-tab-content docutils">
<div class="sd-card sd-sphinx-override sd-mb-3 sd-shadow-sm sd-outline-success sd-rounded-1 sd-font-weight-bold docutils">
<div class="sd-card-header sd-bg-success sd-text-white sd-font-weight-bold docutils">
<p class="sd-card-text">Algorithms Configs</p>
</div>
<div class="sd-card-body docutils">
<div class="admonition note">
<p class="admonition-title">Note</p>
<p class="sd-card-text">The following configs are specific to PPO algorithm.</p>
<ul class="simple">
<li><p class="sd-card-text">clip (float): Clipping parameter for PPO.</p></li>
</ul>
</div>
<ul class="simple">
<li><p class="sd-card-text">steps_per_epoch (int): Number of steps to update the policy network.</p></li>
<li><p class="sd-card-text">update_iters (int): Number of iterations to update the policy network.</p></li>
<li><p class="sd-card-text">batch_size (int): Batch size for each iteration.</p></li>
<li><p class="sd-card-text">target_kl (float): Target KL divergence.</p></li>
<li><p class="sd-card-text">entropy_coef (float): Coefficient of entropy.</p></li>
<li><p class="sd-card-text">reward_normalize (bool): Whether to normalize the reward.</p></li>
<li><p class="sd-card-text">cost_normalize (bool): Whether to normalize the cost.</p></li>
<li><p class="sd-card-text">obs_normalize (bool): Whether to normalize the observation.</p></li>
<li><p class="sd-card-text">kl_early_stop (bool): Whether to stop the training when KL divergence is too large.</p></li>
<li><p class="sd-card-text">max_grad_norm (float): Maximum gradient norm.</p></li>
<li><p class="sd-card-text">use_max_grad_norm (bool): Whether to use maximum gradient norm.</p></li>
<li><p class="sd-card-text">use_critic_norm (bool): Whether to use critic norm.</p></li>
<li><p class="sd-card-text">critic_norm_coef (float): Coefficient of critic norm.</p></li>
<li><p class="sd-card-text">gamma (float): Discount factor.</p></li>
<li><p class="sd-card-text">cost_gamma (float): Cost discount factor.</p></li>
<li><p class="sd-card-text">lam (float): Lambda for GAE-Lambda.</p></li>
<li><p class="sd-card-text">lam_c (float): Lambda for cost GAE-Lambda.</p></li>
<li><p class="sd-card-text">adv_estimation_method (str): The method to estimate the advantage.</p></li>
<li><p class="sd-card-text">standardized_rew_adv (bool): Whether to use standardized reward advantage.</p></li>
<li><p class="sd-card-text">standardized_cost_adv (bool): Whether to use standardized cost advantage.</p></li>
<li><p class="sd-card-text">penalty_coef (float): Penalty coefficient for cost.</p></li>
<li><p class="sd-card-text">use_cost (bool): Whether to use cost.</p></li>
</ul>
</div>
</div>
</div>
<input id="sd-tab-item-6" name="sd-tab-set-2" type="radio">
</input><label class="sd-tab-label" for="sd-tab-item-6">
Model</label><div class="sd-tab-content docutils">
<div class="sd-card sd-sphinx-override sd-mb-3 sd-shadow-sm sd-outline-success sd-rounded-1 sd-font-weight-bold docutils">
<div class="sd-card-header sd-bg-success sd-text-white sd-font-weight-bold docutils">
<p class="sd-card-text">Model Configs</p>
</div>
<div class="sd-card-body docutils">
<ul class="simple">
<li><p class="sd-card-text">weight_initialization_mode (str): The type of weight initialization method.</p></li>
<li><p class="sd-card-text">actor_type (str): The type of actor, default to <code class="docutils literal notranslate"><span class="pre">gaussian_learning</span></code>.</p></li>
<li><p class="sd-card-text">linear_lr_decay (bool): Whether to use linear learning rate decay.</p></li>
<li><p class="sd-card-text">exploration_noise_anneal (bool): Whether to use exploration noise anneal.</p></li>
<li><p class="sd-card-text">std_range (list): The range of standard deviation.</p></li>
</ul>
<div class="admonition hint">
<p class="admonition-title">Hint</p>
<p class="sd-card-text">actor (dictionary): parameters for actor network <code class="docutils literal notranslate"><span class="pre">actor</span></code></p>
<ul class="simple">
<li><p class="sd-card-text">activations: tanh</p></li>
<li><p class="sd-card-text">hidden_sizes:</p></li>
<li><p class="sd-card-text">64</p></li>
<li><p class="sd-card-text">64</p></li>
</ul>
</div>
<div class="admonition hint">
<p class="admonition-title">Hint</p>
<p class="sd-card-text">critic (dictionary): parameters for critic network <code class="docutils literal notranslate"><span class="pre">critic</span></code></p>
<ul class="simple">
<li><p class="sd-card-text">activations: tanh</p></li>
<li><p class="sd-card-text">hidden_sizes:</p></li>
<li><p class="sd-card-text">64</p></li>
<li><p class="sd-card-text">64</p></li>
</ul>
</div>
</div>
</div>
</div>
<input id="sd-tab-item-7" name="sd-tab-set-2" type="radio">
</input><label class="sd-tab-label" for="sd-tab-item-7">
Logger</label><div class="sd-tab-content docutils">
<div class="sd-card sd-sphinx-override sd-mb-3 sd-shadow-sm sd-outline-success sd-rounded-1 sd-font-weight-bold docutils">
<div class="sd-card-header sd-bg-success sd-text-white sd-font-weight-bold docutils">
<p class="sd-card-text">Logger Configs</p>
</div>
<div class="sd-card-body docutils">
<ul class="simple">
<li><p class="sd-card-text">use_wandb (bool): Whether to use wandb to log the training process.</p></li>
<li><p class="sd-card-text">wandb_project (str): The name of wandb project.</p></li>
<li><p class="sd-card-text">use_tensorboard (bool): Whether to use tensorboard to log the training process.</p></li>
<li><p class="sd-card-text">log_dir (str): The directory to save the log files.</p></li>
<li><p class="sd-card-text">window_lens (int): The length of the window to calculate the average reward.</p></li>
<li><p class="sd-card-text">save_model_freq (int): The frequency to save the model.</p></li>
</ul>
</div>
</div>
</div>
</div>
</section>
</section>
</section>
<hr class="docutils" />
<section id="references">
<h2>References<a class="headerlink" href="#references" title="Permalink to this heading">#</a></h2>
<ul class="simple">
<li><p><a class="reference external" href="https://arxiv.org/abs/1502.05477">Trust Region Policy Optimization</a></p></li>
<li><p><a class="reference external" href="https://arxiv.org/pdf/1707.06347.pdf">Proximal Policy Optimization Algorithms</a></p></li>
</ul>
</section>
</section>

        </article>
      </div>
      <footer>
        
        <div class="related-pages">
          <a class="next-page" href="../saferl/cpo.html">
              <div class="page-info">
                <div class="context">
                  <span>Next</span>
                </div>
                <div class="title">Constrained Policy Optimization</div>
              </div>
              <svg class="furo-related-icon"><use href="#svg-arrow-right"></use></svg>
            </a>
          <a class="prev-page" href="trpo.html">
              <svg class="furo-related-icon"><use href="#svg-arrow-right"></use></svg>
              <div class="page-info">
                <div class="context">
                  <span>Previous</span>
                </div>
                
                <div class="title">Trust Region Policy Optimization</div>
                
              </div>
            </a>
        </div>
        <div class="bottom-of-page">
          <div class="left-details">
            <div class="copyright">
                Copyright &#169; 2022, OmniSafe Team
            </div>
            Made with <a href="https://www.sphinx-doc.org/">Sphinx</a> and <a class="muted-link" href="https://pradyunsg.me">@pradyunsg</a>'s
            
            <a href="https://github.com/pradyunsg/furo">Furo</a>
            
          </div>
          <div class="right-details">
            
          </div>
        </div>
        
      </footer>
    </div>
    <aside class="toc-drawer">
      
      
      <div class="toc-sticky toc-scroll">
        <div class="toc-title-container">
          <span class="toc-title">
            On this page
          </span>
        </div>
        <div class="toc-tree-container">
          <div class="toc-tree">
            <ul>
<li><a class="reference internal" href="#">Proximal Policy Optimization</a><ul>
<li><a class="reference internal" href="#quick-facts">Quick Facts</a></li>
<li><a class="reference internal" href="#ppo-theorem">PPO Theorem</a><ul>
<li><a class="reference internal" href="#background">Background</a></li>
<li><a class="reference internal" href="#optimization-objective">Optimization Objective</a></li>
<li><a class="reference internal" href="#ppo-penalty">PPO-Penalty</a></li>
<li><a class="reference internal" href="#ppo-clip">PPO-Clip</a></li>
</ul>
</li>
<li><a class="reference internal" href="#practical-implementation">Practical Implementation</a><ul>
<li><a class="reference internal" href="#generalized-advantage-estimation">Generalized Advantage Estimation</a></li>
<li><a class="reference internal" href="#code-with-omnisafe">Code with OmniSafe</a><ul>
<li><a class="reference internal" href="#quick-start">Quick start</a></li>
<li><a class="reference internal" href="#architecture-of-functions">Architecture of functions</a></li>
<li><a class="reference internal" href="#documentation-of-algorithm-specific-functions">Documentation of algorithm specific functions</a></li>
<li><a class="reference internal" href="#configs">Configs</a></li>
</ul>
</li>
</ul>
</li>
<li><a class="reference internal" href="#references">References</a></li>
</ul>
</li>
</ul>

          </div>
        </div>
      </div>
      
      
    </aside>
  </div>
</div><script data-url_root="../" id="documentation_options" src="../_static/documentation_options.js"></script>
    <script src="../_static/doctools.js"></script>
    <script src="../_static/sphinx_highlight.js"></script>
    <script src="../_static/scripts/furo.js"></script>
    <script src="../_static/clipboard.min.js"></script>
    <script src="../_static/copybutton.js"></script>
    <script src="../_static/design-tabs.js"></script>
    <script async="async" src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>
    </body>
</html>