---
layout: default
title: Code & Data
body_class: page-code
description: Open-source software and data tools from the Neural Computation and Behavior lab.
---

<p class="code-intro">We build open-source tools for acoustic annotation, behavioral experiment control, and multimodal data analysis. Most packages are developed alongside lab projects, but we keep them reusable for researchers working with audio, behavior, and experimental hardware.</p>

<div class="code-projects">
    <article class="code-project">
        <div class="code-project__main">
            <p class="section-kicker">Audio annotation</p>
            <h2><em>DAS</em></h2>
            <p>Deep Audio Segmenter (DAS) annotates song and other acoustic signals directly from raw audio using deep neural networks. It supports single- and multi-channel recordings and can be used through a graphical interface, from the command line, or from Python scripts.</p>
            <ul class="code-project__details">
                <li>Train models from manually annotated recordings and predict song labels on new data.</li>
                <li>Use the GUI for interactive annotation, training, and prediction workflows.</li>
                <li>Run scripted or batch analyses with documented command-line and Python interfaces.</li>
                <li>Follow tutorials, technical notes, and API documentation for adapting DAS to new acoustic datasets.</li>
            </ul>
        </div>
        <aside class="code-project__links" aria-label="DAS resources">
            <p class="code-project__label">Resources</p>
            <a href="https://janclemenslab.org/das">Documentation</a>
            <a href="https://github.com/janclemenslab/das">GitHub repository</a>
            <a href="https://doi.org/10.7554/eLife.68837">Paper</a>
        </aside>
    </article>

    <article class="code-project">
        <div class="code-project__main">
            <p class="section-kicker">Behavioral data</p>
            <h2>xarray-behave</h2>
            <p>xarray-behave provides the data format and graphical interface used by DAS for inspecting and curating multimodal behavioral recordings. It builds on xarray so that signals, annotations, metadata, and aligned measurements can be represented with labeled dimensions instead of loose arrays and sidecar files.</p>
            <ul class="code-project__details">
                <li>Organize behavioral datasets with explicit coordinates, dimensions, and metadata.</li>
                <li>Keep audio, poses, video-derived measurements, stimulus timing, and annotations aligned in one analysis-friendly structure.</li>
                <li>Use the GUI and examples as a starting point for inspecting and curating complex experiments.</li>
                <li>Share reproducible data workflows around a standard Python data model.</li>
            </ul>
        </div>
        <aside class="code-project__links" aria-label="xarray-behave resources">
            <p class="code-project__label">Resources</p>
            <a href="https://github.com/janclemenslab/xarray-behave">GitHub repository</a>
            <a href="https://docs.xarray.dev/">xarray</a>
        </aside>
    </article>

    <article class="code-project">
        <div class="code-project__main">
            <p class="section-kicker">Experiment control</p>
            <h2>etho</h2>
            <p>etho is a Python toolkit for configuring and running behavioral experiments. It focuses on separating experiment protocols, stimulus playlists, hardware configuration, and logging so that setups can be reused across experiments without rewriting control code.</p>
            <ul class="code-project__details">
                <li>Start experiments from the command line or open the graphical interface for interactive control.</li>
                <li>Define global configuration, experiment protocols, and stimulus playlists in separate files.</li>
                <li>Integrate hardware such as cameras, National Instruments DAQmx cards, DLP projectors, Raspberry Pi devices, and ScanImage setups.</li>
                <li>Collect local and broadcast logs from experiment services for debugging and record keeping.</li>
            </ul>
        </div>
        <aside class="code-project__links" aria-label="etho resources">
            <p class="code-project__label">Resources</p>
            <a href="https://janclemenslab.org/etho/">Documentation</a>
            <a href="https://github.com/janclemenslab/etho">GitHub repository</a>
        </aside>
    </article>

    <article class="code-project">
        <div class="code-project__main">
            <p class="section-kicker">More code</p>
            <h2>Other repositories</h2>
            <p>Additional repositories include project-specific analysis code, smaller helper packages, and experimental tools that support ongoing lab work. Publication pages also link to code and data when they are available for a specific study.</p>
            <ul class="code-project__details">
                <li>Browse the lab organization for shared packages, analysis projects, and documentation sources.</li>
                <li>Use repository issues for bug reports, installation problems, or feature requests on maintained projects.</li>
            </ul>
        </div>
        <aside class="code-project__links" aria-label="Additional repository links">
            <p class="code-project__label">Resources</p>
            <a href="https://github.com/janclemenslab">Lab GitHub</a>
        </aside>
    </article>
</div>
