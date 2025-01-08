<h1>File Integrity Monitoring (FIM)</h1>

<h2>Overview</h2>
<ul>
  <li>Created an integrity baseline of target files/folders using the <strong>SHA-512 hashing algorithm</strong>.</li>
  <li>Developed and tested a <strong>custom/proof of concept FIM</strong> solution.</li>
  <li>Compared current file states to the established baseline and raised <strong>Slack alerts</strong> if deviations occurred.</li>
</ul>

<h2>Detailed Steps</h2>

<h3>1. Establish the Integrity Baseline</h3>
<ul>
  <li>
    <strong>Identify Target Files & Folders</strong><br/>
    <ul>
      <li>Determine which critical files and directories need to be monitored (e.g., configuration files, system binaries, scripts).</li>
    </ul>
  </li>
  <li>
    <strong>Generate Baseline Hashes</strong><br/>
    <ul>
      <li>Use the <strong>SHA-512</strong> hashing algorithm to compute a unique hash value for each file in the target list.</li>
      <li>Store these hashes in a secure location (e.g., a database or encrypted file) to serve as the “baseline.”</li>
    </ul>
  </li>
</ul>

<h3>2. Build a Custom/Proof of Concept FIM</h3>
<ul>
  <li>
    <strong>Design Your Monitoring Script or Tool</strong><br/>
    <ul>
      <li>Write a script (e.g., in Python or Bash) or create a small application that scans monitored files on a scheduled basis.</li>
      <li>Include logic for reading stored baseline hashes and comparing them to newly generated hashes.</li>
    </ul>
  </li>
  <li>
    <strong>Implement Efficiency & Error Handling</strong><br/>
    <ul>
      <li>Ensure your script handles file read errors gracefully (e.g., permission issues, missing files).</li>
      <li>Consider multi-threading or incremental scans to reduce system performance impact.</li>
    </ul>
  </li>
</ul>

<h3>3. Continuous Comparison Against Baseline</h3>
<ul>
  <li>
    <strong>Scheduled Scans</strong><br/>
    <ul>
      <li>Automate regular scanning (e.g., via cron jobs or a Windows Task Scheduler).</li>
      <li>Compare the newly computed hash of each file with its original baseline hash.</li>
    </ul>
  </li>
  <li>
    <strong>Raise Alerts on Deviation</strong><br/>
    <ul>
      <li>If the new hash differs from the baseline hash, record the incident (e.g., in a log file or event management system).</li>
      <li>Flag changes as “authorized” or “unauthorized” based on predefined rules or human review.</li>
    </ul>
  </li>
</ul>

<h3>4. Send Alerts via Slack (or Other Channels)</h3>
<ul>
  <li>
    <strong>Slack Integration Setup</strong><br/>
    <ul>
      <li>Create a Slack webhook or use an existing Slack app to post messages to a specific channel.</li>
      <li>Configure your FIM script to send a payload containing file change details (filename, timestamp, old vs. new hash, etc.).</li>
    </ul>
  </li>
  <li>
    <strong>Notify Security Team or Admins</strong><br/>
    <ul>
      <li>Ensure the Slack channel is monitored by relevant personnel for quick response and investigation.</li>
      <li>Maintain a clear alert format (e.g., color-coded messages, severity level) for easy triage.</li>
    </ul>
  </li>
</ul>

<h2>Conclusion</h2>
<p>
  By creating a <strong>SHA-512-based baseline</strong> and continuously comparing file states, this custom/proof of concept FIM helps detect unauthorized or unexpected changes. Integrating alerts through Slack enables immediate notification and investigation, enhancing overall security posture.
</p>
