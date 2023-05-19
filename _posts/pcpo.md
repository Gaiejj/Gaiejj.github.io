---
title: 'Blog Post number 4'
date: 2015-08-14
permalink: /posts/2012/08/blog-post-4/
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
<link rel="index" title="Index" href="../genindex.html" /><link rel="search" title="Search" href="../search.html" /><link rel="next" title="Proximal Policy Optimization" href="ppo.html" /><link rel="prev" title="Lagrange Duality" href="../foundations/lagrange.html" />

    <!-- Generated with Sphinx 6.2.1 and Furo 2023.03.27 -->
        <title>Trust Region Policy Optimization - </title>
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
<li class="toctree-l1 current current-page"><a class="current reference internal" href="#">Trust Region Policy Optimization</a></li>
<li class="toctree-l1"><a class="reference internal" href="ppo.html">Proximal Policy Optimization</a></li>
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
          <section id="trust-region-policy-optimization">
<h1>Trust Region Policy Optimization<a class="headerlink" href="#trust-region-policy-optimization" title="Permalink to this heading">#</a></h1>
<section id="quick-facts">
<h2>Quick Facts<a class="headerlink" href="#quick-facts" title="Permalink to this heading">#</a></h2>
<div class="sd-card sd-sphinx-override sd-mb-3 sd-shadow-sm sd-outline-info sd-rounded-1 docutils">
<div class="sd-card-body sd-font-weight-bold docutils">
<ol class="arabic simple">
<li><p class="sd-card-text">TRPO is an <span class="sd-sphinx-override sd-badge sd-outline-info sd-text-info">on-policy</span> algorithm.</p></li>
<li><p class="sd-card-text">TRPO can be used for environments with both <span class="sd-sphinx-override sd-badge sd-outline-info sd-text-info">discrete</span> and <span class="sd-sphinx-override sd-badge sd-outline-info sd-text-info">continuous</span> action spaces.</p></li>
<li><p class="sd-card-text">TRPO is an improvement work done based on:bdg-info-line:<cite>NPG</cite> .</p></li>
<li><p class="sd-card-text">TRPO is an important theoretical basis for <a class="sd-sphinx-override sd-badge sd-outline-info sd-text-info reference internal" href="../saferl/cpo.html"><span class="doc">CPO</span></a> .</p></li>
<li><p class="sd-card-text">An <a class="sd-sphinx-override sd-badge sd-outline-info sd-text-info reference internal" href="../baserlapi/on_policy.html#trpoapi"><span class="std std-ref">API Documentation</span></a>  is available for TRPO.</p></li>
</ol>
</div>
</div>
</section>
<hr class="docutils" />
<section id="trpo-theorem">
<h2>TRPO Theorem<a class="headerlink" href="#trpo-theorem" title="Permalink to this heading">#</a></h2>
<section id="background">
<h3>Background<a class="headerlink" href="#background" title="Permalink to this heading">#</a></h3>
<p><strong>Trust region policy optimization (TRPO)</strong> is an iterative method for
optimizing policies in reinforcement learning that ensures monotonic
improvements. It works by iteratively finding a local approximation of the
objective return and maximizing the approximated function. However, the new
policy should be constrained within a trust region relative to the current
policy, which is achieved by using KL divergence to measure the distance
between the two policies.</p>
<p>TRPO is well-suited for optimizing comprehensive nonlinear policies such as
neural networks. It is based on the <strong>Natural Policy Gradient (NPG)</strong> method,
which uses conjugate gradient to avoid expensive computational
costs. Furthermore, TRPO incorporates a line search mechanism to ensure that updated policy adhere to the predetermined KL divergence constraint.</p>
<div class="sd-container-fluid sd-sphinx-override sd-mb-4 docutils">
<div class="sd-row sd-row-cols-2 sd-row-cols-xs-2 sd-row-cols-sm-2 sd-row-cols-md-2 sd-row-cols-lg-2 docutils">
<div class="sd-col sd-d-flex-column sd-col-12 sd-col-xs-12 sd-col-sm-6 sd-col-md-6 sd-col-lg-5 docutils">
<div class="sd-card sd-sphinx-override sd-mb-3 sd-shadow-sm sd-outline-warning sd-rounded-1 sd-font-weight-bold docutils">
<div class="sd-card-header sd-bg-warning sd-text-white sd-font-weight-bold docutils">
<p class="sd-card-text">Problems of NPG</p>
</div>
<div class="sd-card-body docutils">
<ul class="simple">
<li><p class="sd-card-text">It is very difficult to calculate the Hessian matrix directly.</p></li>
<li><p class="sd-card-text">Error introduced by Taylor expansion because of the fixed step length.</p></li>
<li><p class="sd-card-text">Low utilization of sampled data.</p></li>
</ul>
</div>
</div>
</div>
<div class="sd-col sd-d-flex-column sd-col-12 sd-col-xs-12 sd-col-sm-6 sd-col-md-6 sd-col-lg-6 docutils">
<div class="sd-card sd-sphinx-override sd-mb-3 sd-shadow-sm sd-outline-primary sd-rounded-1 sd-font-weight-bold docutils">
<div class="sd-card-header sd-bg-primary sd-text-white sd-font-weight-bold docutils">
<p class="sd-card-text">Advantage of TRPO</p>
</div>
<div class="sd-card-body docutils">
<ul class="simple">
<li><p class="sd-card-text">Using conjugate gradient algorithm to compute the Fisher-Vector product.</p></li>
<li><p class="sd-card-text">Using line search algorithm to eliminate the error introduced by Taylor expansion.</p></li>
<li><p class="sd-card-text">Using importance sampling to reuse data.</p></li>
</ul>
</div>
</div>
</div>
</div>
</div>
</section>
<hr class="docutils" />
<section id="performance-difference-over-policies">
<h3>Performance difference over policies<a class="headerlink" href="#performance-difference-over-policies" title="Permalink to this heading">#</a></h3>
<p>In policy optimization, our objective is to ensure that every update leads to a
consistent improvement in the expected return. To accomplish this, we usually
formulate the equation for expected return in a specific format that is both
intuitive and straightforward to manipulate.</p>
<div class="math-wrapper docutils container" id="equation-trpo-eq-1">
<div class="math notranslate nohighlight" id="equation-trpo-eq-1">
<span class="eqno">(1)<a class="headerlink" href="#equation-trpo-eq-1" title="Permalink to this equation">#</a></span>\[J^R(\pi') = J^R(\pi) + \{J^R(\pi') - J^R(\pi)\}\]</div>
</div>
<p>To achieve monotonic improvements, we only need to consider
<span class="math notranslate nohighlight">\(\Delta = J^R(\pi') - J^R(\pi)\)</span> to be non-negative.</p>
<p>As shown in <strong>NPG</strong>, the difference in performance between two policies
<span class="math notranslate nohighlight">\(\pi'\)</span> and <span class="math notranslate nohighlight">\(\pi\)</span> can be expressed as</p>
<div class="sd-card sd-sphinx-override sd-mb-3 sd-shadow-sm sd-card-hover sd-outline-info sd-rounded-1 docutils" id="trpo-theorem-1">
<div class="sd-card-header sd-bg-info sd-text-white sd-font-weight-bold docutils">
<p class="sd-card-text">Theorem 1 (Performance Difference Bound)</p>
</div>
<div class="sd-card-body docutils">
<div class="math-wrapper docutils container" id="equation-trpo-eq-2">
<span id="trpo-eq-2"></span><div class="math notranslate nohighlight" id="equation-trpo-eq-2">
<span id="trpo-eq-2"></span><span class="eqno">(2)<a class="headerlink" href="#equation-trpo-eq-2" title="Permalink to this equation">#</a></span>\[    J^R(\pi') = J^R(\pi) + \mathbb{E}_{\tau \sim \pi'}[\sum_{t=0}^{\infty} \gamma^t A^{R}_{\pi}(s_t,a_t)]\]</div>
</div>
<p class="sd-card-text">where this expectation is taken over trajectories <span class="math notranslate nohighlight">\(\tau=(s_0, a_0, s_1,\\ a_1, \cdots)\)</span>,
and the notation <span class="math notranslate nohighlight">\(\mathbb{E}_{\tau \sim \pi'}[\cdots]\)</span> indicates that actions are sampled from <span class="math notranslate nohighlight">\(\pi'\)</span> to generate <span class="math notranslate nohighlight">\(\tau\)</span>.</p>
</div>
<div class="sd-card-footer sd-font-weight-bold docutils">
<p class="sd-card-text">The proof of the <span class="sd-sphinx-override sd-badge sd-outline-info sd-text-info">Theorem 1</span> can be seen in the <a class="sd-sphinx-override sd-badge sd-bg-info sd-bg-text-info reference internal" href="../saferl/cpo.html#appendix"><span class="std std-ref">Appendix</span></a>, click on this <span class="sd-sphinx-override sd-badge sd-outline-info sd-text-info">card</span> to jump to view.</p>
</div>
<a class="sd-stretched-link reference internal" href="#appendix-theorem1"><span class="std std-ref"></span></a></div>
<p><span class="sd-sphinx-override sd-badge sd-outline-info sd-text-info">Theorem 1</span> is intuitive as the expected discounted reward of
<span class="math notranslate nohighlight">\(\pi'\)</span> can be viewed as the expected discounted reward of <span class="math notranslate nohighlight">\(\pi\)</span>,
and an extra advantage of <span class="math notranslate nohighlight">\(\pi'\)</span> over <span class="math notranslate nohighlight">\(\pi\)</span>.
The latter term accounts for how much <span class="math notranslate nohighlight">\(\pi'\)</span>
can improve over <span class="math notranslate nohighlight">\(\pi\)</span>, which is of our interest.</p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>We can rewrite <span class="sd-sphinx-override sd-badge sd-outline-info sd-text-info">Theorem 1</span> with a sum over states instead of timesteps:</p>
<div class="math-wrapper docutils container" id="equation-trpo-eq-3">
<span id="trpo-eq-3"></span><div class="math notranslate nohighlight" id="equation-trpo-eq-3">
<span id="trpo-eq-3"></span><span class="eqno">(3)<a class="headerlink" href="#equation-trpo-eq-3" title="Permalink to this equation">#</a></span>\[\begin{split}\label{equation: performance in discount visit density}
J^R(\pi') &amp;=J^R(\pi)+\sum_{t=0}^{\infty} \sum_s P\left(s_t=s \mid \pi'\right) \sum_a \pi' (a \mid s) \gamma^t A^{R}_{\pi}(s, a) \\
&amp;=J^R(\pi)+\sum_s \sum_{t=0}^{\infty} \gamma^t P\left(s_t=s \mid \pi' \right) \sum_a \pi'(a \mid s) A^{R}_{\pi}(s, a) \\
&amp;=J^R(\pi)+\sum_s d_{\pi'}(s) \sum_a \pi'(a \mid s) A^{R}_{\pi}(s, a)\end{split}\]</div>
</div>
</div>
<p>This equation implies for any policy <span class="math notranslate nohighlight">\(\pi'\)</span>, if it has a nonnegative
expected advantage at every state <span class="math notranslate nohighlight">\(s\)</span>, i.e.,
<span class="math notranslate nohighlight">\(\sum_a \pi'(a \mid s) A^{R}_{\pi}(s, a) \geq 0\)</span>,
is guaranteed to increase the policy performance <span class="math notranslate nohighlight">\(J^R\)</span>,
or leave it constant in the case
that the expected advantage is zero everywhere.
However, in the approximate setting, it will typically be unavoidable,
due to estimation and approximation errors,
that there will be some states <span class="math notranslate nohighlight">\(s\)</span> for which the expected advantage is
negative, that is,
<span class="math notranslate nohighlight">\(\sum_a \pi'(a \mid s) A^{R}_{\pi}(s, a)&lt;0\)</span>.</p>
</section>
<hr class="docutils" />
<section id="surrogate-function-for-the-objective">
<h3>Surrogate function for the objective<a class="headerlink" href="#surrogate-function-for-the-objective" title="Permalink to this heading">#</a></h3>
<p><a class="reference internal" href="#equation-trpo-eq-3">Eq.3</a> requires information about future state distribution under
<span class="math notranslate nohighlight">\(\pi'\)</span>,
which is usually unknown and difficult to estimate.
The complex dependency of <span class="math notranslate nohighlight">\(d_{\pi'}(s)\)</span> on <span class="math notranslate nohighlight">\(\pi'\)</span> makes
<a class="reference internal" href="#equation-trpo-eq-3">Eq.3</a> difficult to optimize directly.
Instead, we introduce the following local approximation to <span class="math notranslate nohighlight">\(J^R\)</span>:</p>
<div class="math-wrapper docutils container" id="equation-trpo-eq-4">
<span id="trpo-eq-4"></span><div class="math notranslate nohighlight" id="equation-trpo-eq-4">
<span id="trpo-eq-4"></span><span class="eqno">(4)<a class="headerlink" href="#equation-trpo-eq-4" title="Permalink to this equation">#</a></span>\[L_\pi(\pi')=J^R(\pi)+\sum_s d_\pi(s) \sum_a \pi'(a \mid s) A^{R}_{\pi}(s, a)\]</div>
</div>
<p>Here we only replace <span class="math notranslate nohighlight">\(d_{\pi'}\)</span> with <span class="math notranslate nohighlight">\(d_\pi\)</span>.
It has been proved that if the two policy <span class="math notranslate nohighlight">\(\pi'\)</span> and <span class="math notranslate nohighlight">\(\pi\)</span> are
close enough,
<span class="math notranslate nohighlight">\(L_\pi(\pi')\)</span> can be considered as equivalent to <span class="math notranslate nohighlight">\(J^R(\pi')\)</span>.</p>
<div class="sd-card sd-sphinx-override sd-mb-3 sd-shadow-sm sd-card-hover sd-outline-info sd-rounded-1 docutils" id="trpo-corollary-1">
<div class="sd-card-header sd-bg-info sd-text-white sd-font-weight-bold docutils">
<p class="sd-card-text">Corollary 1 (Performance Difference Bound)</p>
</div>
<div class="sd-card-body docutils">
<p class="sd-card-text">Formally, suppose a parameterized policy <span class="math notranslate nohighlight">\(\pi_\theta\)</span>,
where <span class="math notranslate nohighlight">\(\pi_\theta(a \mid s)\)</span> is a differentiable function of the parameter vector <span class="math notranslate nohighlight">\(\theta\)</span>,
then <span class="math notranslate nohighlight">\(L_\pi\)</span> matches <span class="math notranslate nohighlight">\(J^R\)</span> to first order (see <strong>NPG</strong>).
That is, for any parameter value <span class="math notranslate nohighlight">\(\theta_0\)</span>,</p>
<div class="math-wrapper docutils container" id="equation-trpo-eq-5">
<div class="math notranslate nohighlight" id="equation-trpo-eq-5">
<span class="eqno">(5)<a class="headerlink" href="#equation-trpo-eq-5" title="Permalink to this equation">#</a></span>\[L_{\pi_{\theta_0}}\left(\pi_{\theta_0}\right)=J^R\left(\pi_{\theta_0}\right)\]</div>
</div>
<div class="math-wrapper docutils container" id="equation-trpo-eq-6">
<span id="trpo-eq-6"></span><div class="math notranslate nohighlight" id="equation-trpo-eq-6">
<span id="trpo-eq-6"></span><span class="eqno">(6)<a class="headerlink" href="#equation-trpo-eq-6" title="Permalink to this equation">#</a></span>\[\nabla_\theta L_{\pi_{\theta_0}}\left(\pi_\theta\right)|_{\theta=\theta_0}=\left.\nabla_\theta J^R\left(\pi_\theta\right)\right|_{\theta=\theta_0}\]</div>
</div>
</div>
<div class="sd-card-footer sd-font-weight-bold docutils">
<p class="sd-card-text">The proof of the <span class="sd-sphinx-override sd-badge sd-outline-info sd-text-info">Corollary 1</span> can be seen in the <a class="sd-sphinx-override sd-badge sd-bg-info sd-bg-text-info reference internal" href="../saferl/cpo.html#appendix"><span class="std std-ref">Appendix</span></a>, click on this <span class="sd-sphinx-override sd-badge sd-outline-info sd-text-info">card</span> to jump to view.</p>
</div>
<a class="sd-stretched-link reference internal" href="#appendix-corollary1"><span class="std std-ref"></span></a></div>
<p><a class="reference internal" href="#equation-trpo-eq-6">Eq.6</a> implies that a sufficiently small step
<span class="math notranslate nohighlight">\(\pi_{\theta_0} \rightarrow \pi'\)</span> improving
<span class="math notranslate nohighlight">\(L_{\pi_{\theta_{\text {old }}}}\)</span> will also improve <span class="math notranslate nohighlight">\(J^R\)</span>,
but does not give us any guidance on how big of a step to take.</p>
<p>To address this issue, <strong>NPG</strong> proposed a policy updating scheme called
<strong>conservative policy iteration(CPI)</strong>,
which could provide explicit lower bounds on the improvement of <span class="math notranslate nohighlight">\(J^R\)</span>.
To define the conservative policy iteration update,
let <span class="math notranslate nohighlight">\(\pi_{\mathrm{old}}\)</span> denote the current policy,
and let
<span class="math notranslate nohighlight">\(\pi^{*}=\arg \underset{\pi^{*}}{\max} L_{\pi_{\text {old }}}\left(\pi^{*}\right)\)</span>.
The new policy <span class="math notranslate nohighlight">\(\pi_{\text {new }}\)</span>
was defined to be the following mixture:</p>
<div class="math-wrapper docutils container" id="equation-trpo-eq-7">
<div class="math notranslate nohighlight" id="equation-trpo-eq-7">
<span class="eqno">(7)<a class="headerlink" href="#equation-trpo-eq-7" title="Permalink to this equation">#</a></span>\[\pi_{\text {new }}(a \mid s)=(1-\alpha) \pi_{\text {old }}(a \mid s)+\alpha \pi^{*}(a \mid s)\]</div>
</div>
<p>Kakade and Langford derived the following lower bound:</p>
<div class="math-wrapper docutils container" id="equation-trpo-eq-8">
<span id="trpo-eq-8"></span><div class="math notranslate nohighlight" id="equation-trpo-eq-8">
<span id="trpo-eq-8"></span><span class="eqno">(8)<a class="headerlink" href="#equation-trpo-eq-8" title="Permalink to this equation">#</a></span>\[\begin{split}J^R\left(\pi_{\text {new }}\right)  &amp;\geq L_{\pi_{\text {old }}}\left(\pi_{\text {new }}\right)-\frac{2 \epsilon \gamma}{(1-\gamma)^2} \alpha^2  \\
\text { where } \epsilon &amp;=\max _s\left|\mathbb{E}_{a \sim \pi^{*}(a \mid s)}\left[A^{R}_{\pi}(s, a)\right]\right|\end{split}\]</div>
</div>
<p>However, the lower bound in <a class="reference internal" href="#equation-trpo-eq-8">Eq.8</a> only applies to mixture policies,
so it needs to be extended to general policy cases.</p>
</section>
<hr class="docutils" />
<section id="monotonic-improvement-guarantee-for-general-stochastic-policies">
<h3>Monotonic Improvement Guarantee for General Stochastic Policies<a class="headerlink" href="#monotonic-improvement-guarantee-for-general-stochastic-policies" title="Permalink to this heading">#</a></h3>
<p>Based on the theoretical guarantee <a class="reference internal" href="#equation-trpo-eq-16">Eq.16</a> in mixture policies case,
TRPO extends the lower bound to general policies by replacing <span class="math notranslate nohighlight">\(\alpha\)</span>
with a distance measure between <span class="math notranslate nohighlight">\(\pi\)</span> and <span class="math notranslate nohighlight">\(\pi'\)</span>,
and changing the constant <span class="math notranslate nohighlight">\(\epsilon\)</span> appropriately.
The chosen distance measurement is the total variation divergence
(TV divergence),
which is defined by
<span class="math notranslate nohighlight">\(D_{TV}(p \| q)=\frac{1}{2} \sum_i \left|p_i-q_i\right|\)</span>
for discrete probability distributions <span class="math notranslate nohighlight">\(p, q\)</span>.
Define <span class="math notranslate nohighlight">\(D_{\mathrm{TV}}^{\max }(\pi, \pi')\)</span> as</p>
<div class="math-wrapper docutils container" id="equation-trpo-eq-9">
<div class="math notranslate nohighlight" id="equation-trpo-eq-9">
<span class="eqno">(9)<a class="headerlink" href="#equation-trpo-eq-9" title="Permalink to this equation">#</a></span>\[D_{\mathrm{TV}}^{\max}(\pi, \pi')=\max_s D_{\mathrm{TV}}\left(\pi\left(\cdot \mid s\right) \| \pi'\left(\cdot \mid s\right)\right)\]</div>
</div>
<p>And the new bound is derived by introducing the <span class="math notranslate nohighlight">\(\alpha\)</span>-coupling method.</p>
<div class="sd-card sd-sphinx-override sd-mb-3 sd-shadow-sm sd-card-hover sd-outline-info sd-rounded-1 docutils" id="trpo-theorem-2">
<div class="sd-card-header sd-bg-info sd-text-white sd-font-weight-bold docutils">
<p class="sd-card-text">Theorem 2 (Performance Difference Bound derived by <span class="math notranslate nohighlight">\(\alpha\)</span>-coupling method)</p>
</div>
<div class="sd-card-body docutils">
<p class="sd-card-text">Let
<span class="math notranslate nohighlight">\(\alpha=D_{\mathrm{TV}}^{\max }\left(\pi_{\mathrm{old}}, \pi_{\text {new }}\right)\)</span>.
Then the following bound holds:</p>
<div class="math-wrapper docutils container" id="equation-trpo-eq-10">
<div class="math notranslate nohighlight" id="equation-trpo-eq-10">
<span class="eqno">(10)<a class="headerlink" href="#equation-trpo-eq-10" title="Permalink to this equation">#</a></span>\[\begin{split}J^{R}\left(\pi_{\text {new }}\right)  &amp;\geq L_{\pi_{\text {old }}}\left(\pi_{\text {new }}\right)-\frac{4 \epsilon \gamma}{(1-\gamma)^2} \alpha^2 \\
\text { where } \epsilon &amp;=\max _{s, a}\left|A^{R}_{\pi}(s, a)\right|\end{split}\]</div>
</div>
</div>
<div class="sd-card-footer sd-font-weight-bold docutils">
<p class="sd-card-text">The proof of the <span class="sd-sphinx-override sd-badge sd-outline-info sd-text-info">Theorem 2</span> can be seen in the <a class="sd-sphinx-override sd-badge sd-bg-info sd-bg-text-info reference internal" href="../saferl/cpo.html#appendix"><span class="std std-ref">Appendix</span></a>, click on this <span class="sd-sphinx-override sd-badge sd-outline-info sd-text-info">card</span> to jump to view.</p>
</div>
<a class="sd-stretched-link reference internal" href="#appendix-theorem2"><span class="std std-ref"></span></a></div>
<p>The proof extends Kakade and Langford’s result. Using the fact that the random variables from two distributions with total variation
divergence less than <span class="math notranslate nohighlight">\(\alpha\)</span> can be coupled,
so that they are equal with probability <span class="math notranslate nohighlight">\(1-\alpha\)</span>.</p>
<p>Next, we note the following relationship between the total variation divergence
and the <span class="math notranslate nohighlight">\(\mathrm{KL}\)</span> divergence:
<span class="math notranslate nohighlight">\([D_{\mathrm{TV}}(p \| q)]^2 \leq D_{\mathrm{KL}}(p \| q)\)</span>.
Let
<span class="math notranslate nohighlight">\(D_{\mathrm{KL}}^{\max }(\pi, \pi')=\underset{s}{\max} D_{\mathrm{KL}}(\pi(\cdot|s) \| \pi'(\cdot|s))\)</span>.
The following bound then follows directly from <span class="sd-sphinx-override sd-badge sd-outline-info sd-text-info">Theorem 2</span> :</p>
<div class="math-wrapper docutils container" id="equation-trpo-eq-11">
<span id="trpo-eq-11"></span><div class="math notranslate nohighlight" id="equation-trpo-eq-11">
<span id="trpo-eq-11"></span><span class="eqno">(11)<a class="headerlink" href="#equation-trpo-eq-11" title="Permalink to this equation">#</a></span>\[\begin{split}J^R(\pi') &amp; \geq L_\pi(\pi')-C D_{\mathrm{KL}}^{\max }(\pi, \pi') \\
\quad \text { where } C &amp;=\frac{4 \epsilon \gamma}{(1-\gamma)^2}\end{split}\]</div>
</div>
<p>TRPO describes an approximate policy iteration scheme based on the policy
improvement bound in <a class="reference internal" href="#equation-trpo-eq-11">Eq.11</a>.
Note that for now, we assume exact evaluation of the advantage values <span class="math notranslate nohighlight">\(A^{R}_{\pi}\)</span>.</p>
<p>It follows from <a class="reference internal" href="#equation-trpo-eq-11">Eq.11</a> that TRPO is guaranteed to generate a
monotonically improving sequence of policies
<span class="math notranslate nohighlight">\(J^R\left(\pi_0\right) \leq J^R\left(\pi_1\right) \leq J^R\left(\pi_2\right) \leq \cdots \leq J^R\left(\pi_n\right)\)</span>.
To see this, let
<span class="math notranslate nohighlight">\(M_i(\pi)=L_{\pi_i}(\pi)-C D_{\mathrm{KL}}^{\max }\left(\pi_i, \pi\right)\)</span>.
Then</p>
<div class="math-wrapper docutils container" id="equation-trpo-eq-12">
<div class="math notranslate nohighlight" id="equation-trpo-eq-12">
<span class="eqno">(12)<a class="headerlink" href="#equation-trpo-eq-12" title="Permalink to this equation">#</a></span>\[\begin{split}J^{R}\left(\pi_{i+1}\right) &amp;\geq M_i\left(\pi_{i+1}\right) \\
J^{R}\left(\pi_i\right)&amp;=M_i\left(\pi_i\right), \text { therefore, } \\
J^{R}\left(\pi_{i+1}\right)-\eta\left(\pi_i\right)&amp;\geq M_i\left(\pi_{i+1}\right)-M\left(\pi_i\right)\end{split}\]</div>
</div>
<p>Thus, by maximizing <span class="math notranslate nohighlight">\(M_i\)</span> at each iteration, we guarantee that the true
objective <span class="math notranslate nohighlight">\(J^R\)</span> is non-decreasing.</p>
</section>
</section>
<hr class="docutils" id="trust-region-policy-optimization-1" />
<section id="practical-implementation">
<h2>Practical Implementation<a class="headerlink" href="#practical-implementation" title="Permalink to this heading">#</a></h2>
<section id="approximately-solving-the-trpo-update">
<h3>Approximately Solving the TRPO Update<a class="headerlink" href="#approximately-solving-the-trpo-update" title="Permalink to this heading">#</a></h3>
<p>Until now, we present the iteration algorithm with theoretically guaranteed
monotonic improvement for new policy over the current policy.
However, in practice, when we consider policies in parameterized space
<span class="math notranslate nohighlight">\(\pi_{\theta}(a \mid s)\)</span>,
the algorithm cannot work well. By plugging in the notation <span class="math notranslate nohighlight">\(\theta\)</span>, our
update step becomes</p>
<div class="math-wrapper docutils container" id="equation-trpo-eq-13">
<div class="math notranslate nohighlight" id="equation-trpo-eq-13">
<span class="eqno">(13)<a class="headerlink" href="#equation-trpo-eq-13" title="Permalink to this equation">#</a></span>\[\begin{split}&amp; L_{\theta_{old}}(\theta)-C D_{\mathrm{KL}}^{\max }(\theta_{old}, \theta) \\\end{split}\]</div>
</div>
<p>where <span class="math notranslate nohighlight">\(C=\frac{4 \epsilon \gamma}{(1-\gamma)^2}\)</span>,
and <span class="math notranslate nohighlight">\(\theta_{old}, \theta\)</span>
are short for <span class="math notranslate nohighlight">\(\pi_{\theta_{old}}, \pi_{\theta}\)</span>.
In practice, the penalty coefficient <span class="math notranslate nohighlight">\(C\)</span> for KL divergence would produce
a very small step size and the improvement would be too conservative.
To allow larger step size, instead of penalty term on KL divergence,
TRPO uses fixed KL divergence constraint to bound the distance between
<span class="math notranslate nohighlight">\(\pi_{\theta_{old}}\)</span> and <span class="math notranslate nohighlight">\(\pi_{\theta}\)</span>:</p>
<div class="math-wrapper docutils container" id="equation-trpo-eq-14">
<div class="math notranslate nohighlight" id="equation-trpo-eq-14">
<span class="eqno">(14)<a class="headerlink" href="#equation-trpo-eq-14" title="Permalink to this equation">#</a></span>\[\begin{split}\underset{\theta}{\max}\quad  &amp;L_{\theta_{old}}(\theta) \\
\text{s.t. } \quad &amp;D_{\mathrm{KL}}^{\max }(\theta_{old}, \theta) \le \delta\end{split}\]</div>
</div>
<p>This problem imposes a constraint that the KL divergence is bounded at every
point in the state space.
While it is motivated by the theory,
this problem is impractical to solve due to a large number of constraints.
Instead, TRPO uses a heuristic approximation that considers the average KL
divergence:</p>
<div class="math-wrapper docutils container" id="equation-trpo-eq-15">
<div class="math notranslate nohighlight" id="equation-trpo-eq-15">
<span class="eqno">(15)<a class="headerlink" href="#equation-trpo-eq-15" title="Permalink to this equation">#</a></span>\[\begin{split}\underset{\theta}{\max}\quad  &amp;L_{\theta_{old}}(\theta) \label{eq:maxklconst} \\
\text{s.t. } \quad &amp;\bar{D}_{\mathrm{KL}}(\theta_{old}, \theta) \le \delta\end{split}\]</div>
</div>
<p>where
<span class="math notranslate nohighlight">\(\bar{D}_{\mathrm{KL}}:=\mathbb{E}_{s \sim \rho}\left[D_{\mathrm{KL}}\left(\pi_{\theta_1}(\cdot \mid s) \| \pi_{\theta_2}(\cdot \mid s)\right)\right]\)</span>
.The method TRPO describes involves two steps:</p>
<div class="sd-card sd-sphinx-override sd-mb-3 sd-shadow-sm sd-outline-success sd-rounded-1 sd-font-weight-bold docutils">
<div class="sd-card-header sd-bg-success sd-text-white sd-font-weight-bold docutils">
<p class="sd-card-text">Two Steps For TRPO Update</p>
</div>
<div class="sd-card-body docutils">
<ol class="arabic simple">
<li><p class="sd-card-text">Compute a search direction, using a linear approximation to the objective and quadratic approximation to the constraint.</p></li>
<li><p class="sd-card-text">Perform a line search in that direction, ensuring that we improve the nonlinear objective while satisfying the nonlinear constraint.</p></li>
</ol>
</div>
</div>
<div class="sd-container-fluid sd-sphinx-override sd-mb-4 docutils">
<div class="sd-row sd-row-cols-2 sd-row-cols-xs-2 sd-row-cols-sm-2 sd-row-cols-md-2 sd-row-cols-lg-2 docutils">
<div class="sd-col sd-d-flex-column sd-col-12 sd-col-xs-12 sd-col-sm-6 sd-col-md-6 sd-col-lg-5 docutils">
<div class="sd-card sd-sphinx-override sd-mb-3 sd-shadow-sm sd-outline-warning sd-rounded-1 sd-font-weight-bold docutils">
<div class="sd-card-header sd-bg-warning sd-text-white sd-font-weight-bold docutils">
<p class="sd-card-text">Problems</p>
</div>
<div class="sd-card-body docutils">
<ul class="simple">
<li><p class="sd-card-text">It is prohibitively costly to form the full Hessian matrix.</p></li>
<li><p class="sd-card-text">How to compute the maximal step length such that the KL divergence is satisfied ?</p></li>
<li><p class="sd-card-text">How to ensure improvement of the surrogate objective and satisfaction of the KL divergence ?</p></li>
</ul>
</div>
</div>
</div>
<div class="sd-col sd-d-flex-column sd-col-12 sd-col-xs-12 sd-col-sm-6 sd-col-md-6 sd-col-lg-6 docutils">
<div class="sd-card sd-sphinx-override sd-mb-3 sd-shadow-sm sd-outline-primary sd-rounded-1 sd-font-weight-bold docutils">
<div class="sd-card-header sd-bg-primary sd-text-white sd-font-weight-bold docutils">
<p class="sd-card-text">Solutions</p>
</div>
<div class="sd-card-body docutils">
<ul class="simple">
<li><p class="sd-card-text"><a class="sd-sphinx-override sd-badge sd-outline-success sd-text-success reference internal" href="#conjugate"><span class="std std-ref">Conjugate gradient algorithm</span></a> can approximately search the update direction without forming this full Hessian matrix.</p></li>
<li><p class="sd-card-text">The max step size can be formed by an intermediate result produced by the conjugate gradient algorithm.</p></li>
<li><p class="sd-card-text">A <a class="sd-sphinx-override sd-badge sd-outline-success sd-text-success reference internal" href="#conjugate"><span class="std std-ref">line search algorithm</span></a> can be used to meet the goal.</p></li>
</ul>
</div>
</div>
</div>
</div>
</div>
<div class="sd-tab-set docutils">
<input checked="checked" id="sd-tab-item-0" name="sd-tab-set-0" type="radio">
</input><label class="sd-tab-label" for="sd-tab-item-0">
Computing the Fisher-Vector Product</label><div class="sd-tab-content docutils">
<div class="sd-card sd-sphinx-override sd-mb-3 sd-shadow-sm sd-card-hover sd-outline-success sd-rounded-1 docutils">
<div class="sd-card-header sd-bg-success sd-text-white sd-font-weight-bold docutils">
<p class="sd-card-text">Computing the Fisher-Vector Product</p>
</div>
<div class="sd-card-body docutils">
<p class="sd-card-text">TRPO approximately computes the search direction by solving the equation <span class="math notranslate nohighlight">\(Hx=g\)</span>,
where <span class="math notranslate nohighlight">\(H\)</span> is the Fisher information matrix, i.e.,
the quadratic approximation to the KL divergence constraint <span class="math notranslate nohighlight">\(\bar{D}_{\mathrm{KL}}\left(\theta_{\text {old }}, \theta\right) \approx \frac{1}{2}\left(\theta-\theta_{\text {old }}\right)^T H\left(\theta-\theta_{\text {old }}\right)\)</span>,
where <span class="math notranslate nohighlight">\(H_{i j}=\frac{\partial}{\partial \theta_i} \frac{\partial}{\partial \theta_j} \bar{D}_{\mathrm{KL}}\left(\theta_{\text {old }}, \theta\right)\)</span> (according to the definition of matrix <span class="math notranslate nohighlight">\(H\)</span>).
It is very difficult to calculate the entire <span class="math notranslate nohighlight">\(H\)</span> or <span class="math notranslate nohighlight">\(H^{-1}\)</span> directly,
so TRPO uses conjugate gradient algorithm to approximately solve the equation <span class="math notranslate nohighlight">\(Hx=g\)</span> without forming this full matrix.</p>
</div>
<div class="sd-card-footer sd-font-weight-bold docutils">
<p class="sd-card-text">The implementation of <span class="sd-sphinx-override sd-badge sd-outline-success sd-text-success">Computing the Fisher-Vector Product</span> can be seen in the <span class="sd-sphinx-override sd-badge sd-bg-success sd-bg-text-success">Code with OmniSafe</span>, click on this <span class="sd-sphinx-override sd-badge sd-outline-success sd-text-success">card</span> to jump to view.</p>
</div>
<a class="sd-stretched-link reference internal" href="#conjugate"><span class="std std-ref"></span></a></div>
</div>
<input id="sd-tab-item-1" name="sd-tab-set-0" type="radio">
</input><label class="sd-tab-label" for="sd-tab-item-1">
Computing The Final Update Step</label><div class="sd-tab-content docutils">
<div class="sd-card sd-sphinx-override sd-mb-3 sd-shadow-sm sd-card-hover sd-outline-success sd-rounded-1 docutils">
<div class="sd-card-header sd-bg-success sd-text-white sd-font-weight-bold docutils">
<p class="sd-card-text">Computing The Final Update Step</p>
</div>
<div class="sd-card-body docutils">
<p class="sd-card-text">Having computed the search direction <span class="math notranslate nohighlight">\(s\approx H^{-1}g\)</span>,
TRPO next needs to compute the appropriate step length to ensure improvement of the surrogate objective and satisfaction of the KL divergence constraint.
First, TRPO computes the maximal step length <span class="math notranslate nohighlight">\(\beta\)</span> such that <span class="math notranslate nohighlight">\(\beta+\theta s\)</span> will satisfy the KL divergence constraint.
To do this, let <span class="math notranslate nohighlight">\(\delta=\bar{D}_{\mathrm{KL}} \approx \frac{1}{2}(\beta s)^T H(\beta s)=\frac{1}{2} \beta^2 s^T A s\)</span>.
Finally, we obtain <span class="math notranslate nohighlight">\(\beta=\sqrt{2 \delta / s^T H s}\)</span>.</p>
<div class="admonition hint">
<p class="admonition-title">Hint</p>
<p class="sd-card-text">The term <span class="math notranslate nohighlight">\(s^THs\)</span> is an intermediate result produced by the conjugate gradient algorithm.</p>
</div>
<p class="sd-card-text">To meet the constraints, TRPO uses line search algorithm to compute the final step length.
Detailedly, TRPO performs the line search on the objective <span class="math notranslate nohighlight">\(L_{\theta_{\text {old }}}(\theta)-\mathcal{X}\left[\bar{D}_{\text {KL }}\left(\theta_{\text {old }}, \theta\right) \leq \delta\right]\)</span>, where <span class="math notranslate nohighlight">\(\mathcal{X}[\ldots]\)</span> equals to <span class="math notranslate nohighlight">\(0\)</span>,
when its argument is true, and <span class="math notranslate nohighlight">\(+\infty\)</span> when it is false.
Starting with the maximal value of the step length <span class="math notranslate nohighlight">\(\beta\)</span> computed in the previous paragraph,
TRPO shrinks <span class="math notranslate nohighlight">\(\beta\)</span> exponentially until the objective improves. Without this line search,
the algorithm occasionally computes large steps that cause a catastrophic degradation of performance.</p>
</div>
<div class="sd-card-footer sd-font-weight-bold docutils">
<p class="sd-card-text">The implementation of <span class="sd-sphinx-override sd-badge sd-outline-success sd-text-success">Computing The Final Update Step</span> can be seen in the <span class="sd-sphinx-override sd-badge sd-bg-success sd-bg-text-success">Code with OmniSafe</span>, click on this <span class="sd-sphinx-override sd-badge sd-outline-success sd-text-success">card</span> to jump to view.</p>
</div>
<a class="sd-stretched-link reference internal" href="#conjugate"><span class="std std-ref"></span></a></div>
</div>
</div>
</section>
<section id="code-with-omnisafe">
<span id="trpo-code-with-omnisafe"></span><h3>Code with OmniSafe<a class="headerlink" href="#code-with-omnisafe" title="Permalink to this heading">#</a></h3>
<section id="quick-start">
<h4>Quick start<a class="headerlink" href="#quick-start" title="Permalink to this heading">#</a></h4>
<div class="sd-card sd-sphinx-override sd-mb-3 sd-shadow-sm sd-outline-success sd-rounded-1 sd-font-weight-bold docutils">
<div class="sd-card-header sd-bg-success sd-text-white sd-font-weight-bold docutils">
<p class="sd-card-text">Run TRPO in OmniSafe</p>
</div>
<div class="sd-card-body docutils">
<p class="sd-card-text">Here are 3 ways to run TRPO in OmniSafe:</p>
<ul class="simple">
<li><p class="sd-card-text">Run Agent from preset yaml file</p></li>
<li><p class="sd-card-text">Run Agent from custom config dict</p></li>
<li><p class="sd-card-text">Run Agent from custom terminal config</p></li>
</ul>
<div class="sd-tab-set docutils">
<input checked="checked" id="sd-tab-item-2" name="sd-tab-set-1" type="radio">
</input><label class="sd-tab-label" for="sd-tab-item-2">
Yaml file style</label><div class="sd-tab-content docutils">
<div class="highlight-python notranslate"><div class="highlight"><pre><span></span><span class="linenos">1</span><span class="kn">import</span> <span class="nn">omnisafe</span>
<span class="linenos">2</span>
<span class="linenos">3</span>
<span class="linenos">4</span><span class="n">env_id</span> <span class="o">=</span> <span class="s1">&#39;SafetyPointGoal1-v0&#39;</span>
<span class="linenos">5</span>
<span class="linenos">6</span><span class="n">agent</span> <span class="o">=</span> <span class="n">omnisafe</span><span class="o">.</span><span class="n">Agent</span><span class="p">(</span><span class="s1">&#39;TRPO&#39;</span><span class="p">,</span> <span class="n">env_id</span><span class="p">)</span>
<span class="linenos">7</span><span class="n">agent</span><span class="o">.</span><span class="n">learn</span><span class="p">()</span>
</pre></div>
</div>
</div>
<input id="sd-tab-item-3" name="sd-tab-set-1" type="radio">
</input><label class="sd-tab-label" for="sd-tab-item-3">
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
<span class="linenos">20</span><span class="n">agent</span> <span class="o">=</span> <span class="n">omnisafe</span><span class="o">.</span><span class="n">Agent</span><span class="p">(</span><span class="s1">&#39;TRPO&#39;</span><span class="p">,</span> <span class="n">env_id</span><span class="p">,</span> <span class="n">custom_cfgs</span><span class="o">=</span><span class="n">custom_cfgs</span><span class="p">)</span>
<span class="linenos">21</span><span class="n">agent</span><span class="o">.</span><span class="n">learn</span><span class="p">()</span>
</pre></div>
</div>
</div>
<input id="sd-tab-item-4" name="sd-tab-set-1" type="radio">
</input><label class="sd-tab-label" for="sd-tab-item-4">
Terminal config style</label><div class="sd-tab-content docutils">
<p class="sd-card-text">We use <code class="docutils literal notranslate"><span class="pre">train_policy.py</span></code> as the entrance file. You can train the agent with TRPO simply using <code class="docutils literal notranslate"><span class="pre">train_policy.py</span></code>, with arguments about TRPO and environments does the training.
For example, to run TRPO in SafetyPointGoal1-v0 , with 1 torch thread, seed 0 and single environment, you can use the following command:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre><span></span><span class="linenos">1</span><span class="nb">cd</span><span class="w"> </span>examples
<span class="linenos">2</span>python<span class="w"> </span>train_policy.py<span class="w"> </span>--algo<span class="w"> </span>TRPO<span class="w"> </span>--env-id<span class="w"> </span>SafetyPointGoal1-v0<span class="w"> </span>--parallel<span class="w"> </span><span class="m">1</span><span class="w"> </span>--total-steps<span class="w"> </span><span class="m">10000000</span><span class="w"> </span>--device<span class="w"> </span>cpu<span class="w"> </span>--vector-env-nums<span class="w"> </span><span class="m">1</span><span class="w"> </span>--torch-threads<span class="w"> </span><span class="m">1</span>
</pre></div>
</div>
</div>
</div>
</div>
</div>
</section>
<hr class="docutils" />
<section id="architecture-of-functions">
<h4>Architecture of functions<a class="headerlink" href="#architecture-of-functions" title="Permalink to this heading">#</a></h4>
<ul class="simple">
<li><p><code class="docutils literal notranslate"><span class="pre">TRPO.learn()</span></code></p>
<ul>
<li><p><code class="docutils literal notranslate"><span class="pre">TRPO._env.rollout()</span></code></p></li>
<li><p><code class="docutils literal notranslate"><span class="pre">TRPO._update()</span></code></p>
<ul>
<li><p><code class="docutils literal notranslate"><span class="pre">TRPO._buf.get()</span></code></p></li>
<li><p><code class="docutils literal notranslate"><span class="pre">TRPO._update_actor()</span></code></p>
<ul>
<li><p><code class="docutils literal notranslate"><span class="pre">TRPO._fvp()</span></code></p></li>
<li><p><code class="docutils literal notranslate"><span class="pre">conjugate_gradients()</span></code></p></li>
<li><p><code class="docutils literal notranslate"><span class="pre">TRPO._cpo_search_step()</span></code></p></li>
</ul>
</li>
<li><p><code class="docutils literal notranslate"><span class="pre">TRPO._update_reward_critic()</span></code></p></li>
</ul>
</li>
</ul>
</li>
</ul>
<hr class="docutils" />
</section>
<section id="documentation-of-algorithm-specific-functions">
<span id="conjugate"></span><h4>Documentation of algorithm specific functions<a class="headerlink" href="#documentation-of-algorithm-specific-functions" title="Permalink to this heading">#</a></h4>
<div class="sd-tab-set docutils">
<input checked="checked" id="sd-tab-item-5" name="sd-tab-set-2" type="radio">
</input><label class="sd-tab-label" for="sd-tab-item-5">
trpo._fvp()</label><div class="sd-tab-content docutils">
<div class="sd-card sd-sphinx-override sd-mb-3 sd-shadow-sm sd-outline-success sd-rounded-1 sd-font-weight-bold docutils">
<div class="sd-card-header sd-bg-success sd-text-white sd-font-weight-bold docutils">
<p class="sd-card-text">trpo._fvp()</p>
</div>
<div class="sd-card-body docutils">
<p class="sd-card-text">TRPO algorithm builds the Hessian-vector product instead of the full Hessian matrix based on an approximation of the KL-divergence,
flowing the next steps:</p>
<ol class="arabic simple">
<li><p class="sd-card-text">Calculate the KL divergence between two policy.
Note that <code class="docutils literal notranslate"><span class="pre">self._actor_critic.actor</span></code> denotes the actor <span class="math notranslate nohighlight">\(\pi\)</span> and <code class="docutils literal notranslate"><span class="pre">kl</span></code> denotes the KL divergence.</p></li>
</ol>
<div class="highlight-python notranslate"><div class="highlight"><pre><span></span><span class="linenos">1</span><span class="bp">self</span><span class="o">.</span><span class="n">_actor_critic</span><span class="o">.</span><span class="n">actor</span><span class="o">.</span><span class="n">zero_grad</span><span class="p">()</span>
<span class="linenos">2</span><span class="n">q_dist</span> <span class="o">=</span> <span class="bp">self</span><span class="o">.</span><span class="n">_actor_critic</span><span class="o">.</span><span class="n">actor</span><span class="p">(</span><span class="bp">self</span><span class="o">.</span><span class="n">_fvp_obs</span><span class="p">)</span>
<span class="linenos">3</span><span class="k">with</span> <span class="n">torch</span><span class="o">.</span><span class="n">no_grad</span><span class="p">():</span>
<span class="linenos">4</span>    <span class="n">p_dist</span> <span class="o">=</span> <span class="bp">self</span><span class="o">.</span><span class="n">_actor_critic</span><span class="o">.</span><span class="n">actor</span><span class="p">(</span><span class="bp">self</span><span class="o">.</span><span class="n">_fvp_obs</span><span class="p">)</span>
<span class="linenos">5</span><span class="n">kl</span> <span class="o">=</span> <span class="n">torch</span><span class="o">.</span><span class="n">distributions</span><span class="o">.</span><span class="n">kl</span><span class="o">.</span><span class="n">kl_divergence</span><span class="p">(</span><span class="n">p_dist</span><span class="p">,</span> <span class="n">q_dist</span><span class="p">)</span><span class="o">.</span><span class="n">mean</span><span class="p">()</span>
</pre></div>
</div>
<ol class="arabic simple" start="2">
<li><p class="sd-card-text">Use <code class="docutils literal notranslate"><span class="pre">torch.autograd.grad()</span></code> to compute the Hessian-vector product.
Please note that in line 4, we compute the gradient of <code class="docutils literal notranslate"><span class="pre">kl_p</span></code> (The product of the Jacobian of KL divergence and <span class="math notranslate nohighlight">\(g\)</span>) instead of <code class="docutils literal notranslate"><span class="pre">grads</span></code> (The Jacobian of KL divergence)</p></li>
</ol>
<div class="highlight-python notranslate"><div class="highlight"><pre><span></span><span class="linenos"> 1</span><span class="n">grads</span> <span class="o">=</span> <span class="n">torch</span><span class="o">.</span><span class="n">autograd</span><span class="o">.</span><span class="n">grad</span><span class="p">(</span>
<span class="linenos"> 2</span>    <span class="n">kl</span><span class="p">,</span>
<span class="linenos"> 3</span>    <span class="nb">tuple</span><span class="p">(</span><span class="bp">self</span><span class="o">.</span><span class="n">_actor_critic</span><span class="o">.</span><span class="n">actor</span><span class="o">.</span><span class="n">parameters</span><span class="p">()),</span>
<span class="linenos"> 4</span>    <span class="n">create_graph</span><span class="o">=</span><span class="kc">True</span><span class="p">,</span>
<span class="linenos"> 5</span><span class="p">)</span>
<span class="linenos"> 6</span><span class="n">flat_grad_kl</span> <span class="o">=</span> <span class="n">torch</span><span class="o">.</span><span class="n">cat</span><span class="p">([</span><span class="n">grad</span><span class="o">.</span><span class="n">view</span><span class="p">(</span><span class="o">-</span><span class="mi">1</span><span class="p">)</span> <span class="k">for</span> <span class="n">grad</span> <span class="ow">in</span> <span class="n">grads</span><span class="p">])</span>
<span class="linenos"> 7</span>
<span class="linenos"> 8</span><span class="n">kl_p</span> <span class="o">=</span> <span class="p">(</span><span class="n">flat_grad_kl</span> <span class="o">*</span> <span class="n">params</span><span class="p">)</span><span class="o">.</span><span class="n">sum</span><span class="p">()</span>
<span class="linenos"> 9</span><span class="n">grads</span> <span class="o">=</span> <span class="n">torch</span><span class="o">.</span><span class="n">autograd</span><span class="o">.</span><span class="n">grad</span><span class="p">(</span>
<span class="linenos">10</span>    <span class="n">kl_p</span><span class="p">,</span>
<span class="linenos">11</span>    <span class="nb">tuple</span><span class="p">(</span><span class="bp">self</span><span class="o">.</span><span class="n">_actor_critic</span><span class="o">.</span><span class="n">actor</span><span class="o">.</span><span class="n">parameters</span><span class="p">()),</span>
<span class="linenos">12</span>    <span class="n">retain_graph</span><span class="o">=</span><span class="kc">False</span><span class="p">,</span>
<span class="linenos">13</span><span class="p">)</span>
</pre></div>
</div>
<ol class="arabic simple" start="3">
<li><p class="sd-card-text">return the Hessian-vector product.</p></li>
</ol>
<div class="highlight-python notranslate"><div class="highlight"><pre><span></span><span class="linenos">1</span><span class="n">flat_grad_grad_kl</span> <span class="o">=</span> <span class="n">torch</span><span class="o">.</span><span class="n">cat</span><span class="p">([</span><span class="n">grad</span><span class="o">.</span><span class="n">contiguous</span><span class="p">()</span><span class="o">.</span><span class="n">view</span><span class="p">(</span><span class="o">-</span><span class="mi">1</span><span class="p">)</span> <span class="k">for</span> <span class="n">grad</span> <span class="ow">in</span> <span class="n">grads</span><span class="p">])</span>
<span class="linenos">2</span><span class="n">distributed</span><span class="o">.</span><span class="n">avg_tensor</span><span class="p">(</span><span class="n">flat_grad_grad_kl</span><span class="p">)</span>
<span class="linenos">3</span>
<span class="linenos">4</span><span class="k">return</span> <span class="n">flat_grad_grad_kl</span> <span class="o">+</span> <span class="n">params</span> <span class="o">*</span> <span class="bp">self</span><span class="o">.</span><span class="n">_cfgs</span><span class="o">.</span><span class="n">algo_cfgs</span><span class="o">.</span><span class="n">cg_damping</span>
</pre></div>
</div>
</div>
</div>
</div>
<input id="sd-tab-item-6" name="sd-tab-set-2" type="radio">
</input><label class="sd-tab-label" for="sd-tab-item-6">
conjugate_gradients()</label><div class="sd-tab-content docutils">
<div class="sd-card sd-sphinx-override sd-mb-3 sd-shadow-sm sd-outline-success sd-rounded-1 sd-font-weight-bold docutils">
<div class="sd-card-header sd-bg-success sd-text-white sd-font-weight-bold docutils">
<p class="sd-card-text">conjugate_gradients()</p>
</div>
<div class="sd-card-body docutils">
<p class="sd-card-text">TRPO algorithm uses conjugate gradients algorithm to search the update direction with Hessian-vector product,
The conjugate gradient descent method attempts to solve problem <span class="math notranslate nohighlight">\(Hx=g\)</span>
flowing the next steps:</p>
<ol class="arabic simple">
<li><p class="sd-card-text">Set the initial solution <code class="docutils literal notranslate"><span class="pre">x</span></code> and calculate the error <code class="docutils literal notranslate"><span class="pre">r</span></code> between the <code class="docutils literal notranslate"><span class="pre">x</span></code> and the target <code class="docutils literal notranslate"><span class="pre">b_vector</span></code> (<span class="math notranslate nohighlight">\(g\)</span> in above equation). Note that <code class="docutils literal notranslate"><span class="pre">Fvp</span></code> is the Hessian-vector product, which denotes <span class="math notranslate nohighlight">\(H\)</span>.</p></li>
</ol>
<div class="highlight-python notranslate"><div class="highlight"><pre><span></span><span class="linenos">1</span><span class="n">vector_x</span> <span class="o">=</span> <span class="n">torch</span><span class="o">.</span><span class="n">zeros_like</span><span class="p">(</span><span class="n">vector_b</span><span class="p">)</span>
<span class="linenos">2</span><span class="n">vector_r</span> <span class="o">=</span> <span class="n">vector_b</span> <span class="o">-</span> <span class="n">fisher_product</span><span class="p">(</span><span class="n">vector_x</span><span class="p">)</span>
<span class="linenos">3</span><span class="n">vector_p</span> <span class="o">=</span> <span class="n">vector_r</span><span class="o">.</span><span class="n">clone</span><span class="p">()</span>
<span class="linenos">4</span><span class="n">rdotr</span> <span class="o">=</span> <span class="n">torch</span><span class="o">.</span><span class="n">dot</span><span class="p">(</span><span class="n">vector_r</span><span class="p">,</span> <span class="n">vector_r</span><span class="p">)</span>
</pre></div>
</div>
<ol class="arabic simple" start="2">
<li><p class="sd-card-text">Performs <code class="docutils literal notranslate"><span class="pre">n_step</span></code> conjugate gradient.</p></li>
</ol>
<div class="highlight-python notranslate"><div class="highlight"><pre><span></span><span class="linenos"> 1</span><span class="k">for</span> <span class="n">_</span> <span class="ow">in</span> <span class="nb">range</span><span class="p">(</span><span class="n">num_steps</span><span class="p">):</span>
<span class="linenos"> 2</span>    <span class="n">vector_z</span> <span class="o">=</span> <span class="n">fisher_product</span><span class="p">(</span><span class="n">vector_p</span><span class="p">)</span>
<span class="linenos"> 3</span>    <span class="n">alpha</span> <span class="o">=</span> <span class="n">rdotr</span> <span class="o">/</span> <span class="p">(</span><span class="n">torch</span><span class="o">.</span><span class="n">dot</span><span class="p">(</span><span class="n">vector_p</span><span class="p">,</span> <span class="n">vector_z</span><span class="p">)</span> <span class="o">+</span> <span class="n">eps</span><span class="p">)</span>
<span class="linenos"> 4</span>    <span class="n">vector_x</span> <span class="o">+=</span> <span class="n">alpha</span> <span class="o">*</span> <span class="n">vector_p</span>
<span class="linenos"> 5</span>    <span class="n">vector_r</span> <span class="o">-=</span> <span class="n">alpha</span> <span class="o">*</span> <span class="n">vector_z</span>
<span class="linenos"> 6</span>    <span class="n">new_rdotr</span> <span class="o">=</span> <span class="n">torch</span><span class="o">.</span><span class="n">dot</span><span class="p">(</span><span class="n">vector_r</span><span class="p">,</span> <span class="n">vector_r</span><span class="p">)</span>
<span class="linenos"> 7</span>    <span class="k">if</span> <span class="n">torch</span><span class="o">.</span><span class="n">sqrt</span><span class="p">(</span><span class="n">new_rdotr</span><span class="p">)</span> <span class="o">&lt;</span> <span class="n">residual_tol</span><span class="p">:</span>
<span class="linenos"> 8</span>        <span class="k">break</span>
<span class="linenos"> 9</span>    <span class="n">vector_mu</span> <span class="o">=</span> <span class="n">new_rdotr</span> <span class="o">/</span> <span class="p">(</span><span class="n">rdotr</span> <span class="o">+</span> <span class="n">eps</span><span class="p">)</span>
<span class="linenos">10</span>    <span class="n">vector_p</span> <span class="o">=</span> <span class="n">vector_r</span> <span class="o">+</span> <span class="n">vector_mu</span> <span class="o">*</span> <span class="n">vector_p</span>
<span class="linenos">11</span>    <span class="n">rdotr</span> <span class="o">=</span> <span class="n">new_rdotr</span>
<span class="linenos">12</span><span class="k">return</span> <span class="n">vector_x</span>
</pre></div>
</div>
<ol class="arabic simple" start="3">
<li><p class="sd-card-text">Return the solution of <span class="math notranslate nohighlight">\(x\)</span> without computing <span class="math notranslate nohighlight">\(x=H^{-1}g\)</span>.</p></li>
</ol>
</div>
</div>
</div>
<input id="sd-tab-item-7" name="sd-tab-set-2" type="radio">
</input><label class="sd-tab-label" for="sd-tab-item-7">
trpo._search_step_size()</label><div class="sd-tab-content docutils">
<div class="sd-card sd-sphinx-override sd-mb-3 sd-shadow-sm sd-outline-success sd-rounded-1 sd-font-weight-bold docutils">
<div class="sd-card-header sd-bg-success sd-text-white sd-font-weight-bold docutils">
<p class="sd-card-text">trpo._search_step_size()</p>
</div>
<div class="sd-card-body docutils">
<p class="sd-card-text">TRPO algorithm performs line-search to ensure constraint satisfaction for rewards and costs,
and search around for a satisfied step of policy update to improve loss and reward performance,
flowing the next steps:</p>
<ol class="arabic simple">
<li><p class="sd-card-text">Get the current policy parameters and initialize the step size.</p></li>
</ol>
<div class="highlight-python notranslate"><div class="highlight"><pre><span></span><span class="linenos">1</span><span class="c1"># How far to go in a single update</span>
<span class="linenos">2</span><span class="n">step_frac</span> <span class="o">=</span> <span class="mf">1.0</span>
<span class="linenos">3</span><span class="c1"># Get old parameterized policy expression</span>
<span class="linenos">4</span><span class="n">theta_old</span> <span class="o">=</span> <span class="n">get_flat_params_from</span><span class="p">(</span><span class="bp">self</span><span class="o">.</span><span class="n">_actor_critic</span><span class="o">.</span><span class="n">actor</span><span class="p">)</span>
</pre></div>
</div>
<ol class="arabic simple" start="2">
<li><p class="sd-card-text">Calculate the expected reward improvement.</p></li>
</ol>
<div class="highlight-python notranslate"><div class="highlight"><pre><span></span><span class="linenos">1</span><span class="n">expected_improve</span> <span class="o">=</span> <span class="n">g_flat</span><span class="o">.</span><span class="n">dot</span><span class="p">(</span><span class="n">step_dir</span><span class="p">)</span>
</pre></div>
</div>
<ol class="arabic simple" start="3">
<li><p class="sd-card-text">Performs line-search to find a step improve the surrogate while not violating trust region.</p></li>
</ol>
<ul class="simple">
<li><p class="sd-card-text">Search acceptance step ranging from 0 to total step.</p></li>
</ul>
<div class="highlight-python notranslate"><div class="highlight"><pre><span></span><span class="linenos">1</span><span class="c1"># While not within_trust_region and not out of total_steps:</span>
<span class="linenos">2</span><span class="k">for</span> <span class="n">step</span> <span class="ow">in</span> <span class="nb">range</span><span class="p">(</span><span class="n">total_steps</span><span class="p">):</span>
<span class="linenos">3</span>    <span class="c1"># update theta params</span>
<span class="linenos">4</span>    <span class="n">new_theta</span> <span class="o">=</span> <span class="n">theta_old</span> <span class="o">+</span> <span class="n">step_frac</span> <span class="o">*</span> <span class="n">step_direction</span>
<span class="linenos">5</span>    <span class="c1"># set new params as params of net</span>
<span class="linenos">6</span>    <span class="n">set_param_values_to_model</span><span class="p">(</span><span class="bp">self</span><span class="o">.</span><span class="n">_actor_critic</span><span class="o">.</span><span class="n">actor</span><span class="p">,</span> <span class="n">new_theta</span><span class="p">)</span>
</pre></div>
</div>
<ul class="simple">
<li><p class="sd-card-text">In each step of for loop, calculate the policy performance and KL divergence.</p></li>
</ul>
<div class="highlight-python notranslate"><div class="highlight"><pre><span></span><span class="linenos">1</span><span class="k">with</span> <span class="n">torch</span><span class="o">.</span><span class="n">no_grad</span><span class="p">():</span>
<span class="linenos">2</span>    <span class="n">loss</span><span class="p">,</span> <span class="n">_</span> <span class="o">=</span> <span class="bp">self</span><span class="o">.</span><span class="n">_loss_pi</span><span class="p">(</span><span class="n">obs</span><span class="p">,</span> <span class="n">act</span><span class="p">,</span> <span class="n">logp</span><span class="p">,</span> <span class="n">adv</span><span class="p">)</span>
<span class="linenos">3</span>    <span class="c1"># compute KL distance between new and old policy</span>
<span class="linenos">4</span>    <span class="n">q_dist</span> <span class="o">=</span> <span class="bp">self</span><span class="o">.</span><span class="n">_actor_critic</span><span class="o">.</span><span class="n">actor</span><span class="p">(</span><span class="n">obs</span><span class="p">)</span>
<span class="linenos">5</span>    <span class="c1"># KL-distance of old p-dist and new q-dist, applied in KLEarlyStopping</span>
<span class="linenos">6</span>    <span class="n">kl</span> <span class="o">=</span> <span class="n">torch</span><span class="o">.</span><span class="n">distributions</span><span class="o">.</span><span class="n">kl</span><span class="o">.</span><span class="n">kl_divergence</span><span class="p">(</span><span class="n">p_dist</span><span class="p">,</span> <span class="n">q_dist</span><span class="p">)</span><span class="o">.</span><span class="n">mean</span><span class="p">()</span><span class="o">.</span><span class="n">item</span><span class="p">()</span>
<span class="linenos">7</span>    <span class="n">kl</span> <span class="o">=</span> <span class="n">distributed</span><span class="o">.</span><span class="n">dist_avg</span><span class="p">(</span><span class="n">kl</span><span class="p">)</span>
</pre></div>
</div>
<ul class="simple">
<li><p class="sd-card-text">Step only if surrogate is improved and within the trust region.</p></li>
</ul>
<div class="highlight-python notranslate"><div class="highlight"><pre><span></span><span class="linenos"> 1</span><span class="c1"># real loss improve: old policy loss - new policy loss</span>
<span class="linenos"> 2</span><span class="n">loss_improve</span> <span class="o">=</span> <span class="n">loss_before</span> <span class="o">-</span> <span class="n">loss</span><span class="o">.</span><span class="n">item</span><span class="p">()</span>
<span class="linenos"> 3</span><span class="c1"># average processes.... multi-processing style like: mpi_tools.mpi_avg(xxx)</span>
<span class="linenos"> 4</span><span class="n">loss_improve</span> <span class="o">=</span> <span class="n">distributed</span><span class="o">.</span><span class="n">dist_avg</span><span class="p">(</span><span class="n">loss_improve</span><span class="p">)</span>
<span class="linenos"> 5</span><span class="bp">self</span><span class="o">.</span><span class="n">_logger</span><span class="o">.</span><span class="n">log</span><span class="p">(</span><span class="sa">f</span><span class="s1">&#39;Expected Improvement: </span><span class="si">{</span><span class="n">expected_improve</span><span class="si">}</span><span class="s1"> Actual: </span><span class="si">{</span><span class="n">loss_improve</span><span class="si">}</span><span class="s1">&#39;</span><span class="p">)</span>
<span class="linenos"> 6</span><span class="k">if</span> <span class="ow">not</span> <span class="n">torch</span><span class="o">.</span><span class="n">isfinite</span><span class="p">(</span><span class="n">loss</span><span class="p">):</span>
<span class="linenos"> 7</span>    <span class="bp">self</span><span class="o">.</span><span class="n">_logger</span><span class="o">.</span><span class="n">log</span><span class="p">(</span><span class="s1">&#39;WARNING: loss_pi not finite&#39;</span><span class="p">)</span>
<span class="linenos"> 8</span><span class="k">elif</span> <span class="n">loss_improve</span> <span class="o">&lt;</span> <span class="mi">0</span><span class="p">:</span>
<span class="linenos"> 9</span>    <span class="bp">self</span><span class="o">.</span><span class="n">_logger</span><span class="o">.</span><span class="n">log</span><span class="p">(</span><span class="s1">&#39;INFO: did not improve improve &lt;0&#39;</span><span class="p">)</span>
<span class="linenos">10</span><span class="k">elif</span> <span class="n">kl</span> <span class="o">&gt;</span> <span class="bp">self</span><span class="o">.</span><span class="n">_cfgs</span><span class="o">.</span><span class="n">algo_cfgs</span><span class="o">.</span><span class="n">target_kl</span><span class="p">:</span>
<span class="linenos">11</span>    <span class="bp">self</span><span class="o">.</span><span class="n">_logger</span><span class="o">.</span><span class="n">log</span><span class="p">(</span><span class="s1">&#39;INFO: violated KL constraint.&#39;</span><span class="p">)</span>
<span class="linenos">12</span><span class="k">else</span><span class="p">:</span>
<span class="linenos">13</span>    <span class="c1"># step only if surrogate is improved and when within trust reg.</span>
<span class="linenos">14</span>    <span class="n">acceptance_step</span> <span class="o">=</span> <span class="n">step</span> <span class="o">+</span> <span class="mi">1</span>
<span class="linenos">15</span>    <span class="bp">self</span><span class="o">.</span><span class="n">_logger</span><span class="o">.</span><span class="n">log</span><span class="p">(</span><span class="sa">f</span><span class="s1">&#39;Accept step at i=</span><span class="si">{</span><span class="n">acceptance_step</span><span class="si">}</span><span class="s1">&#39;</span><span class="p">)</span>
<span class="linenos">16</span>    <span class="k">break</span>
</pre></div>
</div>
<ol class="arabic simple" start="3">
<li><p class="sd-card-text">Return appropriate step direction and acceptance step.</p></li>
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
<input checked="checked" id="sd-tab-item-8" name="sd-tab-set-3" type="radio">
</input><label class="sd-tab-label" for="sd-tab-item-8">
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
<input id="sd-tab-item-9" name="sd-tab-set-3" type="radio">
</input><label class="sd-tab-label" for="sd-tab-item-9">
Algorithm</label><div class="sd-tab-content docutils">
<div class="sd-card sd-sphinx-override sd-mb-3 sd-shadow-sm sd-outline-success sd-rounded-1 sd-font-weight-bold docutils">
<div class="sd-card-header sd-bg-success sd-text-white sd-font-weight-bold docutils">
<p class="sd-card-text">Algorithms Configs</p>
</div>
<div class="sd-card-body docutils">
<div class="admonition note">
<p class="admonition-title">Note</p>
<p class="sd-card-text">The following configs are specific to TRPO algorithm.</p>
<ul class="simple">
<li><p class="sd-card-text">cg_damping (float): Damping coefficient for conjugate gradient.</p></li>
<li><p class="sd-card-text">cg_iters (int): Number of iterations for conjugate gradient.</p></li>
<li><p class="sd-card-text">fvp_sample_freq (int): Frequency of sampling for Fisher vector product.</p></li>
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
<input id="sd-tab-item-10" name="sd-tab-set-3" type="radio">
</input><label class="sd-tab-label" for="sd-tab-item-10">
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
<input id="sd-tab-item-11" name="sd-tab-set-3" type="radio">
</input><label class="sd-tab-label" for="sd-tab-item-11">
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
<section id="reference">
<h2>Reference<a class="headerlink" href="#reference" title="Permalink to this heading">#</a></h2>
<ul class="simple">
<li><p><a class="reference external" href="https://proceedings.neurips.cc/paper/2001/file/4b86abe48d358ecf194c56c69108433e-Paper.pdf">A Natural Policy
Gradient</a></p></li>
<li><p><a class="reference external" href="https://arxiv.org/abs/1502.05477">Trust Region Policy
Optimization</a></p></li>
</ul>
</section>
<section id="appendix">
<h2>Appendix<a class="headerlink" href="#appendix" title="Permalink to this heading">#</a></h2>
<p><a class="sd-sphinx-override sd-badge sd-outline-info sd-text-info reference internal" href="#trpo-theorem-1"><span class="std std-ref">Click here to jump to TRPO Theorem</span></a></p>
<p><a class="sd-sphinx-override sd-badge sd-outline-success sd-text-success reference internal" href="#trpo-code-with-omnisafe"><span class="std std-ref">Click here to jump to Code withOmniSafe</span></a></p>
<section id="proof-of-theorem-1-difference-between-two-arbitrary-policies">
<span id="appendix-theorem1"></span><h3>Proof of Theorem 1 (Difference between two arbitrary policies)<a class="headerlink" href="#proof-of-theorem-1-difference-between-two-arbitrary-policies" title="Permalink to this heading">#</a></h3>
<div class="sd-card sd-sphinx-override sd-mb-3 sd-shadow-sm sd-outline-info sd-rounded-1 docutils">
<div class="sd-card-header sd-bg-info sd-text-white sd-font-weight-bold docutils">
<p class="sd-card-text">Proof of Theorem 1</p>
</div>
<div class="sd-card-body docutils">
<p class="sd-card-text">First note that <span class="math notranslate nohighlight">\(A^{R}_{\pi}(s, a)=\mathbb{E}_{s' \sim \mathbb{P}\left(s^{\prime} \mid s, a\right)}\left[r(s)+\gamma V^R_{\pi}\left(s^{\prime}\right)-V^R_{\pi}(s)\right]\)</span>.
Therefore,</p>
<div class="math-wrapper docutils container" id="equation-trpo-eq-16">
<span id="trpo-eq-15"></span><div class="math notranslate nohighlight" id="equation-trpo-eq-16">
<span id="trpo-eq-15"></span><span class="eqno">(16)<a class="headerlink" href="#equation-trpo-eq-16" title="Permalink to this equation">#</a></span>\[\begin{split}\mathbb{E}_{\tau \sim \pi'}\left[\sum_{t=0}^{\infty} \gamma^t A^{R}_{\pi}\left(s_t, a_t\right)\right] &amp;=\mathbb{E}_{\tau \sim \pi'}\left[\sum _ { t = 0 } ^ { \infty } \gamma ^ { t } \left(r\left(s_t\right)+\gamma V^{R}_{\pi}\left(s_{t+1}\right)-V^{R}_{\pi}\left(s_{t} \right)\right) \right] \\
&amp;=\mathbb{E}_{\tau \sim \pi'}\left[-V^R_{\pi}\left(s_0\right)+\sum_{t=0}^{\infty} \gamma^t r\left(s_t\right)\right] \\
&amp;=-\mathbb{E}_{s_0}\left[V^R_{\pi}\left(s_0\right)\right]+\mathbb{E}_{\tau \sim \pi'}\left[\sum_{t=0}^{\infty} \gamma^t r\left(s_t\right)\right] \\
&amp;=-J^R(\pi)+J^R(\pi')\end{split}\]</div>
</div>
</div>
</div>
</section>
<section id="proof-of-corollary-1">
<span id="appendix-corollary1"></span><h3>Proof of Corollary 1<a class="headerlink" href="#proof-of-corollary-1" title="Permalink to this heading">#</a></h3>
<div class="sd-card sd-sphinx-override sd-mb-3 sd-shadow-sm sd-outline-info sd-rounded-1 docutils">
<div class="sd-card-header sd-bg-info sd-text-white sd-font-weight-bold docutils">
<p class="sd-card-text">Proof of Corollary 1</p>
</div>
<div class="sd-card-body docutils">
<p class="sd-card-text">From <a class="reference internal" href="#equation-trpo-eq-2">Eq.2</a> and <a class="reference internal" href="#equation-trpo-eq-4">Eq.4</a> , we can easily know that</p>
<div class="math-wrapper docutils container" id="equation-trpo-eq-17">
<div class="math notranslate nohighlight" id="equation-trpo-eq-17">
<span class="eqno">(17)<a class="headerlink" href="#equation-trpo-eq-17" title="Permalink to this equation">#</a></span>\[\begin{split}&amp; L_{\pi_{\theta_0}}\left(\pi_{\theta_0}\right)=J^{R}\left(\pi_{\theta_0}\right)\quad \\
\text{since}~~ &amp;\sum_s \rho_\pi(s) \sum_a \pi'(a \mid s) A^{R}_{\pi}(s, a)=0.\end{split}\]</div>
</div>
<p class="sd-card-text">Now <a class="reference internal" href="#equation-trpo-eq-4">Eq.4</a> can be written as follows:</p>
<div class="math-wrapper docutils container" id="equation-trpo-eq-18">
<div class="math notranslate nohighlight" id="equation-trpo-eq-18">
<span class="eqno">(18)<a class="headerlink" href="#equation-trpo-eq-18" title="Permalink to this equation">#</a></span>\[J^{R}\left(\pi^{'}_{\theta}\right) = J^{R}(\pi_{\theta_0}) + \sum_s d_{\pi^{'}_{\theta}}(s) \sum_a \pi^{'}_{\theta}(a|s) A^{R}_{\pi_{\theta_0}}(s,a)\]</div>
</div>
<p class="sd-card-text">So,</p>
<div class="math-wrapper docutils container" id="equation-trpo-eq-19">
<span id="trpo-eq-18"></span><div class="math notranslate nohighlight" id="equation-trpo-eq-19">
<span id="trpo-eq-18"></span><span class="eqno">(19)<a class="headerlink" href="#equation-trpo-eq-19" title="Permalink to this equation">#</a></span>\[\begin{split}\nabla_{\theta} J^{R}(\pi_{\theta})|_{\theta = \theta_0} &amp;= J^{R}(\pi_{\theta_0}) + \sum_s \nabla d_{\pi_{\theta}}(s) \sum_a \pi_{\theta}(a|s) A^{R}_{\pi_{\theta_0}}(s,a)+\sum_s d_{\pi_{\theta}}(s) \sum_a \nabla \pi_{\theta}(a|s) A^{R}_{\pi_{\theta_0}}(s,a) \\
&amp;= J^{R}(\pi_{\theta_0}) + \sum_s d_{\pi_{\theta}}(s) \sum_a \nabla \pi_{\theta}(a|s) A^{R}_{\pi_{\theta_0}}(s,a)\end{split}\]</div>
</div>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p class="sd-card-text"><span class="math notranslate nohighlight">\(\sum_s \nabla d_{\pi_{\theta}}(s) \sum_a \pi_{\theta}(a|s) A^{R}_{\pi_{\theta_0}}(s,a)=0\)</span></p>
</div>
<p class="sd-card-text">Meanwhile,</p>
<div class="math-wrapper docutils container" id="equation-trpo-eq-20">
<span id="trpo-eq-19"></span><div class="math notranslate nohighlight" id="equation-trpo-eq-20">
<span id="trpo-eq-19"></span><span class="eqno">(20)<a class="headerlink" href="#equation-trpo-eq-20" title="Permalink to this equation">#</a></span>\[L_{\pi_{\theta_0}}(\pi_{\theta})=J^{R}(\pi_{\theta_0})+\sum_s d_{\pi_{\theta_0}}(s) \sum_a \pi_{\theta}(a \mid s) A^{R}_{\pi_{\theta_0}}(s, a)\]</div>
</div>
<p class="sd-card-text">So,</p>
<div class="math-wrapper docutils container" id="equation-trpo-eq-21">
<div class="math notranslate nohighlight" id="equation-trpo-eq-21">
<span class="eqno">(21)<a class="headerlink" href="#equation-trpo-eq-21" title="Permalink to this equation">#</a></span>\[\nabla L_{\pi_{\theta_0}}(\pi_{\theta}) | _{\theta = \theta_0}=J^{R}(\pi_{\theta_0})+\sum_s d_{\pi_{\theta_0}}(s) \sum_a \nabla \pi_{\theta}(a \mid s) A^{R}_{\pi_{\theta_0}}(s, a)\]</div>
</div>
<p class="sd-card-text">Combine <a class="reference internal" href="#equation-trpo-eq-19">Eq.19</a>  and
<a class="reference internal" href="#equation-trpo-eq-20">Eq.20</a>, we have</p>
<div class="math-wrapper docutils container" id="equation-trpo-eq-22">
<div class="math notranslate nohighlight" id="equation-trpo-eq-22">
<span class="eqno">(22)<a class="headerlink" href="#equation-trpo-eq-22" title="Permalink to this equation">#</a></span>\[\left.\nabla_\theta L_{\pi_{\theta_0}}\left(\pi_\theta\right)\right|_{\theta=\theta_0}=\left.\nabla_\theta J^{R}\left(\pi_\theta\right)\right|_{\theta=\theta_0}\]</div>
</div>
</div>
</div>
</section>
<section id="proof-of-theorem-2-difference-between-two-arbitrary-policies">
<span id="appendix-theorem2"></span><h3>Proof of Theorem 2 (Difference between two arbitrary policies)<a class="headerlink" href="#proof-of-theorem-2-difference-between-two-arbitrary-policies" title="Permalink to this heading">#</a></h3>
<p>Define <span class="math notranslate nohighlight">\(\bar{A}^R(s)\)</span> to be the expected advantage of <span class="math notranslate nohighlight">\(\pi'\)</span> over <span class="math notranslate nohighlight">\(\pi\)</span> at <span class="math notranslate nohighlight">\(s\)</span>,</p>
<div class="math-wrapper docutils container" id="equation-trpo-eq-23">
<div class="math notranslate nohighlight" id="equation-trpo-eq-23">
<span class="eqno">(23)<a class="headerlink" href="#equation-trpo-eq-23" title="Permalink to this equation">#</a></span>\[\bar{A}^R(s)=\mathbb{E}_{a \sim \pi^{'}(\cdot \mid s)}\left[A^{R}_{\pi}(s, a)\right]\]</div>
</div>
<p><span class="sd-sphinx-override sd-badge sd-outline-info sd-text-info">Theorem 1</span> can be written as follows:</p>
<div class="math-wrapper docutils container" id="equation-trpo-eq-24">
<div class="math notranslate nohighlight" id="equation-trpo-eq-24">
<span class="eqno">(24)<a class="headerlink" href="#equation-trpo-eq-24" title="Permalink to this equation">#</a></span>\[J^R(\pi')=J^R(\pi)+\mathbb{E}_{\tau \sim \pi'}\left[\sum_{t=0}^{\infty} \gamma^t \bar{A}^R\left(s_t\right)\right]\]</div>
</div>
<p>Note that <span class="math notranslate nohighlight">\(L_\pi\)</span> can be written as</p>
<div class="math-wrapper docutils container" id="equation-trpo-eq-25">
<div class="math notranslate nohighlight" id="equation-trpo-eq-25">
<span class="eqno">(25)<a class="headerlink" href="#equation-trpo-eq-25" title="Permalink to this equation">#</a></span>\[L_\pi(\pi')=J^R(\pi)+\mathbb{E}_{\tau \sim \pi}\left[\sum_{t=0}^{\infty} \gamma^t \bar{A}^R\left(s_t\right)\right]\]</div>
</div>
<p>To bound the difference between <span class="math notranslate nohighlight">\(J^R(\pi')\)</span> and <span class="math notranslate nohighlight">\(L_\pi(\pi')\)</span>,
we will bound the difference arising from each timestep.
To do this, we first need to introduce a measure of how much <span class="math notranslate nohighlight">\(\pi\)</span> and
<span class="math notranslate nohighlight">\(\pi'\)</span> agree.
Specifically, we’ll couple the policies,
so that define a joint distribution over pairs of actions.</p>
<div class="sd-card sd-sphinx-override sd-mb-3 sd-shadow-sm sd-outline-info sd-rounded-1 docutils">
<div class="sd-card-header sd-bg-info sd-text-white sd-font-weight-bold docutils">
<p class="sd-card-text">Definition 1</p>
</div>
<div class="sd-card-body docutils">
<p class="sd-card-text"><span class="math notranslate nohighlight">\((\pi, \pi')\)</span> is an <span class="math notranslate nohighlight">\(\alpha\)</span>-coupled policy pair if it
defines a joint distribution <span class="math notranslate nohighlight">\((a, a')|s\)</span>, such that
<span class="math notranslate nohighlight">\(P(a \neq a'|s) \leq \alpha\)</span> for all s.
<span class="math notranslate nohighlight">\(\pi\)</span> and <span class="math notranslate nohighlight">\(\pi'\)</span> will denote the marginal distributions of a and <span class="math notranslate nohighlight">\(a'\)</span>, respectively.</p>
</div>
</div>
<p>Computationally, <span class="math notranslate nohighlight">\(\alpha\)</span>-coupling means that if we randomly choose a
seed for our random number generator,
and then we sample from each of <span class="math notranslate nohighlight">\(\pi\)</span> and <span class="math notranslate nohighlight">\(\pi'\)</span> after setting that
seed,
the results will agree for at least fraction <span class="math notranslate nohighlight">\(1-\alpha\)</span> of seeds.</p>
<div class="sd-tab-set docutils">
<input checked="checked" id="sd-tab-item-12" name="sd-tab-set-4" type="radio">
</input><label class="sd-tab-label" data-sync-id="key1" for="sd-tab-item-12">
Lemma 1</label><div class="sd-tab-content docutils">
<div class="sd-card sd-sphinx-override sd-mb-3 sd-shadow-sm sd-outline-info sd-rounded-1 docutils">
<div class="sd-card-header sd-bg-info sd-text-white sd-font-weight-bold docutils">
<p class="sd-card-text">Lemma 1</p>
</div>
<div class="sd-card-body docutils">
<p class="sd-card-text">Given that <span class="math notranslate nohighlight">\(\pi, \pi'\)</span> are <span class="math notranslate nohighlight">\(\alpha\)</span>-coupled policies,
for all s,</p>
<div class="math-wrapper docutils container" id="equation-trpo-eq-26">
<span id="trpo-eq-25"></span><div class="math notranslate nohighlight" id="equation-trpo-eq-26">
<span id="trpo-eq-25"></span><span class="eqno">(26)<a class="headerlink" href="#equation-trpo-eq-26" title="Permalink to this equation">#</a></span>\[|\bar{A}^R(s)| \leq 2 \alpha \max _{s, a}\left|A^{R}_{\pi}(s, a)\right|\]</div>
</div>
</div>
</div>
</div>
<input id="sd-tab-item-13" name="sd-tab-set-4" type="radio">
</input><label class="sd-tab-label" data-sync-id="key2" for="sd-tab-item-13">
Lemma 2</label><div class="sd-tab-content docutils">
<div class="sd-card sd-sphinx-override sd-mb-3 sd-shadow-sm sd-outline-info sd-rounded-1 docutils">
<div class="sd-card-header sd-bg-info sd-text-white sd-font-weight-bold docutils">
<p class="sd-card-text">Lemma 2</p>
</div>
<div class="sd-card-body docutils">
<p class="sd-card-text">Let <span class="math notranslate nohighlight">\((\pi, \pi')\)</span> be an <span class="math notranslate nohighlight">\(\alpha\)</span>-coupled policy pair.
Then</p>
<div class="math-wrapper docutils container" id="equation-trpo-eq-27">
<div class="math notranslate nohighlight" id="equation-trpo-eq-27">
<span class="eqno">(27)<a class="headerlink" href="#equation-trpo-eq-27" title="Permalink to this equation">#</a></span>\[\begin{split}\left|\mathbb{E}_{s_t \sim \pi'}\left[\bar{A}^R\left(s_t\right)\right]-\mathbb{E}_{s_t \sim \pi}\left[\bar{A}^R\left(s_t\right)\right]\right|&amp;\leq 2 \alpha \max _s \bar{A}^R(s) \\
&amp;\leq 4 \alpha\left(1-(1-\alpha)^t\right) \max _s\left|A^{R}_{\pi}(s, a)\right|\end{split}\]</div>
</div>
</div>
</div>
</div>
</div>
<div class="sd-tab-set docutils">
<input checked="checked" id="sd-tab-item-14" name="sd-tab-set-5" type="radio">
</input><label class="sd-tab-label" data-sync-id="key1" for="sd-tab-item-14">
Proof of Lemma 1</label><div class="sd-tab-content docutils">
<div class="sd-card sd-sphinx-override sd-mb-3 sd-shadow-sm sd-outline-info sd-rounded-1 docutils">
<div class="sd-card-header sd-bg-info sd-text-white sd-font-weight-bold docutils">
<p class="sd-card-text">Proof of Lemma 1</p>
</div>
<div class="sd-card-body docutils">
<div class="math-wrapper docutils container" id="equation-trpo-eq-28">
<span id="trpo-eq-26"></span><div class="math notranslate nohighlight" id="equation-trpo-eq-28">
<span id="trpo-eq-26"></span><span class="eqno">(28)<a class="headerlink" href="#equation-trpo-eq-28" title="Permalink to this equation">#</a></span>\[\begin{split}\bar{A}^R(s) &amp;= \mathbb{E}_{\tilde{a} \sim \tilde{\pi}}\left[A^{R}_{\pi}(s, \tilde{a})\right] - \mathbb{E}_{a \sim \pi}\left[A^{R}_{\pi}(s, a)\right] \\
&amp;=\mathbb{E}_{(a, \tilde{a}) \sim(\pi, \tilde{\pi})}\left[A^{R}_{\pi}(s, \tilde{a})-A^{R}_{\pi}(s, a)\right]\\
&amp;= P(a \neq \tilde{a} \mid s) \mathbb{E}_{(a, \tilde{a}) \sim(\pi, \tilde{\pi}) \mid a \neq \tilde{a}}\left[A^{R}_{\pi}(s, \tilde{a})-A^{R}_{\pi}(s, a)\right]\end{split}\]</div>
</div>
<p class="sd-card-text">So,</p>
<div class="math-wrapper docutils container" id="equation-trpo-eq-29">
<div class="math notranslate nohighlight" id="equation-trpo-eq-29">
<span class="eqno">(29)<a class="headerlink" href="#equation-trpo-eq-29" title="Permalink to this equation">#</a></span>\[|\bar{A}^R(s)|  \leq \alpha \cdot 2 \max _{s, a}\left|A^{R}_{\pi}(s, a)\right|\]</div>
</div>
</div>
</div>
</div>
<input id="sd-tab-item-15" name="sd-tab-set-5" type="radio">
</input><label class="sd-tab-label" data-sync-id="key2" for="sd-tab-item-15">
Proof of Lemma 2</label><div class="sd-tab-content docutils">
<div class="sd-card sd-sphinx-override sd-mb-3 sd-shadow-sm sd-outline-info sd-rounded-1 docutils">
<div class="sd-card-header sd-bg-info sd-text-white sd-font-weight-bold docutils">
<p class="sd-card-text">Proof of Lemma 2</p>
</div>
<div class="sd-card-body docutils">
<p class="sd-card-text">Given the coupled policy pair <span class="math notranslate nohighlight">\((\pi, \pi')\)</span>,
we can also obtain a coupling over the trajectory distributions produced by <span class="math notranslate nohighlight">\(\pi\)</span> and <span class="math notranslate nohighlight">\(\pi'\)</span>,
respectively. Namely, we have pairs of trajectories <span class="math notranslate nohighlight">\(\tau, \tau'\)</span>,
where <span class="math notranslate nohighlight">\(\tau\)</span> is obtained by taking actions from <span class="math notranslate nohighlight">\(\pi\)</span>,
and <span class="math notranslate nohighlight">\(\tau'\)</span> is obtained by taking actions from <span class="math notranslate nohighlight">\(\pi'\)</span>,
where the same random seed is used to generate both trajectories.
We will consider the advantage of <span class="math notranslate nohighlight">\(\pi'\)</span> over <span class="math notranslate nohighlight">\(\pi\)</span> at timestep <span class="math notranslate nohighlight">\(t\)</span>,
and decompose this expectation based on whether <span class="math notranslate nohighlight">\(\pi\)</span> agrees with <span class="math notranslate nohighlight">\(\pi'\)</span> at all timesteps <span class="math notranslate nohighlight">\(i&lt;t\)</span></p>
<p class="sd-card-text">Let <span class="math notranslate nohighlight">\(n_t\)</span> denote the number of times that <span class="math notranslate nohighlight">\(a_i \neq a^{'}_i\)</span> for <span class="math notranslate nohighlight">\(i&lt;t\)</span>,
i.e., the number of times that <span class="math notranslate nohighlight">\(\pi\)</span> and <span class="math notranslate nohighlight">\(\pi'\)</span> disagree before timestep <span class="math notranslate nohighlight">\(t\)</span>.</p>
<div class="math-wrapper docutils container" id="equation-trpo-eq-30">
<div class="math notranslate nohighlight" id="equation-trpo-eq-30">
<span class="eqno">(30)<a class="headerlink" href="#equation-trpo-eq-30" title="Permalink to this equation">#</a></span>\[\begin{split}\mathbb{E}_{s_t \sim \pi'}\left[\bar{A}^R\left(s_t\right)\right]&amp;=P\left(n_t=0\right) \mathbb{E}_{s_t \sim \pi' \mid n_t=0}\left[\bar{A}^R\left(s_t\right)\right]\\
&amp;+P\left(n_t&gt;0\right) \mathbb{E}_{s_t \sim \pi' \mid n_t&gt;0}\left[\bar{A}^R\left(s_t\right)\right]\end{split}\]</div>
</div>
<p class="sd-card-text">The expectation decomposes similarly for actions are sampled using
<span class="math notranslate nohighlight">\(\pi\)</span> :</p>
<div class="math-wrapper docutils container" id="equation-trpo-eq-31">
<div class="math notranslate nohighlight" id="equation-trpo-eq-31">
<span class="eqno">(31)<a class="headerlink" href="#equation-trpo-eq-31" title="Permalink to this equation">#</a></span>\[\begin{split}\mathbb{E}_{s_t \sim \pi}\left[\bar{A}^R\left(s_t\right)\right]&amp;=P\left(n_t=0\right) \mathbb{E}_{s_t \sim \pi \mid n_t=0}\left[\bar{A}^R\left(s_t\right)\right]\\
&amp;+P\left(n_t&gt;0\right) \mathbb{E}_{s_t \sim \pi \mid n_t&gt;0}\left[\bar{A}^R\left(s_t\right)\right]\end{split}\]</div>
</div>
<p class="sd-card-text">Note that the <span class="math notranslate nohighlight">\(n_t=0\)</span> terms are equal:</p>
<div class="math-wrapper docutils container" id="equation-trpo-eq-32">
<div class="math notranslate nohighlight" id="equation-trpo-eq-32">
<span class="eqno">(32)<a class="headerlink" href="#equation-trpo-eq-32" title="Permalink to this equation">#</a></span>\[\mathbb{E}_{s_t \sim \pi' \mid n_t=0}\left[\bar{A}^R\left(s_t\right)\right]=\mathbb{E}_{s_t \sim \pi \mid n_t=0}\left[\bar{A}^R\left(s_t\right)\right]\]</div>
</div>
<p class="sd-card-text">because <span class="math notranslate nohighlight">\(n_t=0\)</span> indicates that <span class="math notranslate nohighlight">\(\pi\)</span> and <span class="math notranslate nohighlight">\(\pi'\)</span> agreed on all timesteps less than <span class="math notranslate nohighlight">\(t\)</span>.
Subtracting Equations <a class="reference internal" href="#equation-trpo-eq-26">Eq.26</a> and <a class="reference internal" href="#equation-trpo-eq-27">Eq.27</a>, we get</p>
<div class="math-wrapper docutils container" id="equation-trpo-eq-33">
<span id="trpo-eq-32"></span><div class="math notranslate nohighlight" id="equation-trpo-eq-33">
<span id="trpo-eq-32"></span><span class="eqno">(33)<a class="headerlink" href="#equation-trpo-eq-33" title="Permalink to this equation">#</a></span>\[\begin{split}&amp;\mathbb{E}_{s_t \sim \pi'}\left[\bar{A}^R\left(s_t\right)\right]-\mathbb{E}_{s_t \sim \pi}\left[\bar{A}^R\left(s_t\right)\right]
\\
=&amp;P\left(n_t&gt;0\right)\left(\mathbb{E}_{s_t \sim \pi' \mid n_t&gt;0}\left[\bar{A}^R\left(s_t\right)\right]-\mathbb{E}_{s_t \sim \pi \mid n_t&gt;0}\left[\bar{A}^R\left(s_t\right)\right]\right)
\label{equation: sub for unfold}\end{split}\]</div>
</div>
<p class="sd-card-text">By definition of <span class="math notranslate nohighlight">\(\alpha, P(\pi, \pi'\)</span> agree at timestep <span class="math notranslate nohighlight">\(i) \geq 1-\alpha\)</span>,
so <span class="math notranslate nohighlight">\(P\left(n_t=0\right) \geq(1-\alpha)^t\)</span>, and</p>
<div class="math-wrapper docutils container" id="equation-trpo-eq-34">
<span id="trpo-eq-33"></span><div class="math notranslate nohighlight" id="equation-trpo-eq-34">
<span id="trpo-eq-33"></span><span class="eqno">(34)<a class="headerlink" href="#equation-trpo-eq-34" title="Permalink to this equation">#</a></span>\[P\left(n_t&gt;0\right) \leq 1-(1-\alpha)^t
\label{equation: probability with a couple policy}\]</div>
</div>
<p class="sd-card-text">Next, note that</p>
<div class="math-wrapper docutils container" id="equation-trpo-eq-35">
<span id="trpo-eq-34"></span><div class="math notranslate nohighlight" id="equation-trpo-eq-35">
<span id="trpo-eq-34"></span><span class="eqno">(35)<a class="headerlink" href="#equation-trpo-eq-35" title="Permalink to this equation">#</a></span>\[\begin{split}&amp;\left|\mathbb{E}_{s_t \sim \pi' \mid n_t&gt;0}\left[\bar{A}^R\left(s_t\right)\right]-\mathbb{E}_{s_t \sim \pi \mid n_t&gt;0}\left[\bar{A}^R\left(s_t\right)\right]\right| \\
&amp; \leq\left|\mathbb{E}_{s_t \sim \pi' \mid n_t&gt;0}\left[\bar{A}^R\left(s_t\right)\right]\right|+\left|\mathbb{E}_{s_t \sim \pi \mid n_t&gt;0}\left[\bar{A}^R\left(s_t\right)\right]\right| \\
&amp; \leq 4 \alpha \max _{s, a}\left|A^{R}_{\pi}(s, a)\right|
\label{equation: abs performance bound nt geq 0}\end{split}\]</div>
</div>
<p class="sd-card-text">Where the second inequality follows from Lemma 2.
Plugging <a class="reference internal" href="#equation-trpo-eq-34">Eq.34</a> and <a class="reference internal" href="#equation-trpo-eq-35">Eq.35</a> into <a class="reference internal" href="#equation-trpo-eq-33">Eq.33</a>, we get</p>
<div class="math-wrapper docutils container" id="equation-trpo-eq-36">
<div class="math notranslate nohighlight" id="equation-trpo-eq-36">
<span class="eqno">(36)<a class="headerlink" href="#equation-trpo-eq-36" title="Permalink to this equation">#</a></span>\[\left|\mathbb{E}_{s_t \sim \pi'}\left[\bar{A}^R\left(s_t\right)\right]-\mathbb{E}_{s_t \sim \pi}\left[\bar{A}^R\left(s_t\right)\right]\right| \leq 4 \alpha\left(1-(1-\alpha)^t\right) \max _{s, a}\left|A^{R}_{\pi}(s, a)\right|\]</div>
</div>
</div>
</div>
</div>
</div>
<p>The preceding Lemma bounds the difference in expected advantage at each
timestep <span class="math notranslate nohighlight">\(t\)</span>.
We can sum over time to bound the difference between <span class="math notranslate nohighlight">\(J^R(\pi')\)</span> and
<span class="math notranslate nohighlight">\(L_\pi(\pi')\)</span>. Subtracting <a class="reference internal" href="#equation-trpo-eq-24">Eq.24</a> and <a class="reference internal" href="#equation-trpo-eq-25">Eq.25</a>,
and defining <span class="math notranslate nohighlight">\(\epsilon=\max _{s, a}\left|A^{R}_{\pi}(s, a)\right|\)</span>, we have</p>
<div class="math-wrapper docutils container" id="equation-trpo-eq-37">
<span id="trpo-eq-36"></span><div class="math notranslate nohighlight" id="equation-trpo-eq-37">
<span id="trpo-eq-36"></span><span class="eqno">(37)<a class="headerlink" href="#equation-trpo-eq-37" title="Permalink to this equation">#</a></span>\[\begin{split}\left|J^R(\pi')-L_\pi(\pi')\right| &amp;=\sum_{t=0}^{\infty} \gamma^t\left|\mathbb{E}_{\tau \sim \pi'}\left[\bar{A}^R\left(s_t\right)\right]-\mathbb{E}_{\tau \sim \pi}\left[\bar{A}^R\left(s_t\right)\right]\right|  \\
&amp; \leq \sum_{t=0}^{\infty} \gamma^t \cdot 4 \epsilon \alpha\left(1-(1-\alpha)^t\right)  \\
&amp;=4 \epsilon \alpha\left(\frac{1}{1-\gamma}-\frac{1}{1-\gamma(1-\alpha)}\right)  \\
&amp;=\frac{4 \alpha^2 \gamma \epsilon}{(1-\gamma)(1-\gamma(1-\alpha))}  \\
&amp; \leq \frac{4 \alpha^2 \gamma \epsilon}{(1-\gamma)^2} \label{TRPO: difference between L and J}\end{split}\]</div>
</div>
<p>Last, to replace <span class="math notranslate nohighlight">\(\alpha\)</span> by the total variation divergence,
we need to use the correspondence between TV divergence and coupled random
variables:</p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>Suppose <span class="math notranslate nohighlight">\(p_X\)</span> and <span class="math notranslate nohighlight">\(p_Y\)</span> are distributions with
<span class="math notranslate nohighlight">\(D_{T V}\left(p_X \| p_Y\right)=\alpha\)</span>. Then there exists a
joint distribution <span class="math notranslate nohighlight">\((X, Y)\)</span> whose marginals are
<span class="math notranslate nohighlight">\(p_X, p_Y\)</span>, for which <span class="math notranslate nohighlight">\(X=Y\)</span> with probability
<span class="math notranslate nohighlight">\(1-\alpha\)</span>. More details in See (Levin et al., 2009),
Proposition 4.7.</p>
</div>
<p>It follows that if we have two policies <span class="math notranslate nohighlight">\(\pi\)</span> and <span class="math notranslate nohighlight">\(\pi'\)</span>
such that</p>
<div class="math-wrapper docutils container" id="equation-trpo-eq-38">
<div class="math notranslate nohighlight" id="equation-trpo-eq-38">
<span class="eqno">(38)<a class="headerlink" href="#equation-trpo-eq-38" title="Permalink to this equation">#</a></span>\[\max_s D_{\mathrm{TV}}(\pi(\cdot|s) \| \pi'(\cdot|s)) \leq \alpha\]</div>
</div>
<p>then we can define an <span class="math notranslate nohighlight">\(\alpha\)</span>-coupled policy pair <span class="math notranslate nohighlight">\((\pi, \pi')\)</span>
with appropriate marginals.
Taking
<span class="math notranslate nohighlight">\(\alpha=\underset{s}{\max} D_{T V}\left(\pi(\cdot \mid s) \| \pi'(\cdot \mid s)\right)\)</span>
in <a class="reference internal" href="#equation-trpo-eq-37">Eq.37</a>, <span class="sd-sphinx-override sd-badge sd-outline-info sd-text-info">Theorem 2</span> follows.</p>
</section>
</section>
</section>

        </article>
      </div>
      <footer>
        
        <div class="related-pages">
          <a class="next-page" href="ppo.html">
              <div class="page-info">
                <div class="context">
                  <span>Next</span>
                </div>
                <div class="title">Proximal Policy Optimization</div>
              </div>
              <svg class="furo-related-icon"><use href="#svg-arrow-right"></use></svg>
            </a>
          <a class="prev-page" href="../foundations/lagrange.html">
              <svg class="furo-related-icon"><use href="#svg-arrow-right"></use></svg>
              <div class="page-info">
                <div class="context">
                  <span>Previous</span>
                </div>
                
                <div class="title">Lagrange Duality</div>
                
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
<li><a class="reference internal" href="#">Trust Region Policy Optimization</a><ul>
<li><a class="reference internal" href="#quick-facts">Quick Facts</a></li>
<li><a class="reference internal" href="#trpo-theorem">TRPO Theorem</a><ul>
<li><a class="reference internal" href="#background">Background</a></li>
<li><a class="reference internal" href="#performance-difference-over-policies">Performance difference over policies</a></li>
<li><a class="reference internal" href="#surrogate-function-for-the-objective">Surrogate function for the objective</a></li>
<li><a class="reference internal" href="#monotonic-improvement-guarantee-for-general-stochastic-policies">Monotonic Improvement Guarantee for General Stochastic Policies</a></li>
</ul>
</li>
<li><a class="reference internal" href="#practical-implementation">Practical Implementation</a><ul>
<li><a class="reference internal" href="#approximately-solving-the-trpo-update">Approximately Solving the TRPO Update</a></li>
<li><a class="reference internal" href="#code-with-omnisafe">Code with OmniSafe</a><ul>
<li><a class="reference internal" href="#quick-start">Quick start</a></li>
<li><a class="reference internal" href="#architecture-of-functions">Architecture of functions</a></li>
<li><a class="reference internal" href="#documentation-of-algorithm-specific-functions">Documentation of algorithm specific functions</a></li>
<li><a class="reference internal" href="#configs">Configs</a></li>
</ul>
</li>
</ul>
</li>
<li><a class="reference internal" href="#reference">Reference</a></li>
<li><a class="reference internal" href="#appendix">Appendix</a><ul>
<li><a class="reference internal" href="#proof-of-theorem-1-difference-between-two-arbitrary-policies">Proof of Theorem 1 (Difference between two arbitrary policies)</a></li>
<li><a class="reference internal" href="#proof-of-corollary-1">Proof of Corollary 1</a></li>
<li><a class="reference internal" href="#proof-of-theorem-2-difference-between-two-arbitrary-policies">Proof of Theorem 2 (Difference between two arbitrary policies)</a></li>
</ul>
</li>
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