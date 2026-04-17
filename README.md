# OCP Claude Skills

OpenShift automation via FastMCP for Claude Code.
First OpenShift skill in the Claude ecosystem.

## What It Does
| Skill | Tools |
|---|---|
| login_status | check_login, ocp_login |
| pod_status | get_pods, get_nodes, get_cluster_operators, get_cluster_version |
| nginx_deploy | deploy_nginx, get_nginx_route |

## Requirements
- Claude Code installed
- oc CLI installed and in PATH
- Python 3.10+
- python3.12 -m pip install -r requirements.txt  
       or
- python3.12 -m pip install fastmcp



## Install
git clone https://github.com/YOUR_NAME/ocp-claude-skills
cd ocp-claude-skills
pip install fastmcp
claude   # starts automatically via .mcp.json

## Usage (just speak naturally)
"Am I logged into OCP?"
"Show me pods in namespace monitoring"
"Are all cluster operators healthy?"
"Deploy nginx in the dev namespace"  #### not done yet

## Tested On
- OCP 4.18
- RHEL 9
- oc CLI 4.18


#####################################  Tested output #########################################################33


[root@ansible-rhel9 ocp-claude-skills]# python3.12 ocp_mcp_server.py


                                                          ╭──────────────────────────────────────────────────────────────────────────────╮
                                                          │                                                                              │
                                                          │                                                                              │
                                                          │                         ▄▀▀ ▄▀█ █▀▀ ▀█▀ █▀▄▀█ █▀▀ █▀█                        │
                                                          │                         █▀  █▀█ ▄▄█  █  █ ▀ █ █▄▄ █▀▀                        │
                                                          │                                                                              │
                                                          │                                                                              │
                                                          │                                                                              │
                                                          │                                FastMCP 3.2.4                                 │
                                                          │                            https://gofastmcp.com                             │
                                                          │                                                                              │
                                                          │                  🖥  Server:      ocp-mcp, 3.2.4                              │
                                                          │                  🚀 Deploy free: https://horizon.prefect.io                  │
                                                          │                                                                              │
                                                          ╰──────────────────────────────────────────────────────────────────────────────╯


[04/17/26 08:21:10] INFO     Starting MCP server 'ocp-mcp' with transport 'stdio'                                                                                                   transport.py:209


[root@ansible-rhel9 ocp-claude-skills]# claude

────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
 Accessing workspace:

 /ocp-claude-skills

 Quick safety check: Is this a project you created or one you trust? (Like your own code, a well-known open source project, or work from your team). If not, take a moment to
 review what's in this folder first.

 Claude Code'll be able to read, edit, and execute files here.

 Security guide

 ❯ 1. Yes, I trust this folder
   2. No, exit

 Enter to confirm · Esc to cancel



────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
  New MCP server found in .mcp.json: ocp-mcp

  MCP servers may execute code or access system resources. All tool calls require approval. Learn more in the MCP documentation.

  ❯ 1. Use this and all future MCP servers in this project
    2. Use this MCP server
    3. Continue without using this MCP server

  Enter to confirm · Esc to cancel



▒ Claude Code           Claude Code v2.1.112
 ▐▛███▜▌   Sonnet 4.6 · API Usage Billing
▝▜█████▛▘  /ocp-claude-skills
  ▘▘ ▝▝    Welcome to Opus 4.7 xhigh! · /effort to tune speed vs. intelligence

────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
❯ /mcp
────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
/mcp                                   Manage MCP servers
/ocp-mcp:pod_health_prompt (MCP)       Prompt to analyze pod health in a namespace (arguments: namespace)
/ocp-mcp:login_status_prompt (MCP)     Prompt to summarize OCP login and cluster health
/ocp-mcp:nginx_deploy_prompt (MCP)     Prompt to deploy and verify nginx on OCP (arguments: namespace)
/less-permission-prompts               Scan your transcripts for common read-only Bash and MCP tool calls, then add a prioritized allowlist to project .claude/settings.jso…

############ Prompt test #######################33

[.......
# Test 1 — Login check
"Am I logged into OCP?"

.......]



           Claude Code v2.1.112
 ▐▛███▜▌   Sonnet 4.6 · API Usage Billing
▝▜█████▛▘  /ocp-claude-skills
  ▘▘ ▝▝    Welcome to Opus 4.7 xhigh! · /effort to tune speed vs. intelligence

❯ Am I logged into OCP?

● Skill(login_status)
  ⎿  Successfully loaded skill

● Checking your OCP login status now.

● Calling ocp-mcp… (ctrl+o to expand)

────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
 Tool use

   ocp-mcp - check_login() (MCP)
   Check if currently logged into OCP — returns current user and server

 Do you want to proceed?
 ❯ 1. Yes
   2. Yes, and don't ask again for ocp-mcp - check_login commands in /ocp-claude-skills
   3. No

 Esc to cancel · Tab to amend

● Skill(login_status)
  ⎿  Successfully loaded skill

● Checking your OCP login status now.

  Called ocp-mcp (ctrl+o to expand)

● Yes, you're logged in. You are authenticated as ocpadmin on the cluster at https://api.vmwocp.xxx.local:6443.




[ .....

# Test 2 — Cluster health
"Show me all nodes"
........ ]

❯ Show me all nodes

● Calling ocp-mcp… (ctrl+o to expand)

────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
 Tool use
    Check OpenShift Container Platform login status
   ocp-mcp - get_nodes() (MCP)
   Get all OCP nodes and their status

 Do you want to proceed?
 ❯ 1. Yes
   2. Yes, and don't ask again for ocp-mcp - get_nodes commands in /ocp-claude-skills
   3. No

 Esc to cancel · Tab to amend
❯ Show me all nodes

  Called ocp-mcp (ctrl+o to expand)

● Your cluster has 6 nodes, all in Ready status:

  ┌───────────────┬───────────────────────┬────────────────┬──────────┐
  │     Name      │         Role          │       IP       │ Version  │
  ├───────────────┼───────────────────────┼────────────────┼──────────┤
  │ vmocp-master1 │ control-plane, master │ 10.254.105.108 │ v1.31.11 │
  ├───────────────┼───────────────────────┼────────────────┼──────────┤
  │ vmocp-master2 │ control-plane, master │ 10.254.105.109 │ v1.31.11 │
  ├───────────────┼───────────────────────┼────────────────┼──────────┤
  │ vmocp-master3 │ control-plane, master │ 10.254.105.110 │ v1.31.11 │
  ├───────────────┼───────────────────────┼────────────────┼──────────┤
  │ vmocp-worker1 │ worker                │ 10.254.105.111 │ v1.31.11 │
  ├───────────────┼───────────────────────┼────────────────┼──────────┤
  │ vmocp-worker2 │ worker                │ 10.254.105.112 │ v1.31.11 │
  ├───────────────┼───────────────────────┼────────────────┼──────────┤
  │ vmocp-worker3 │ worker                │ 10.254.105.113 │ v1.31.11 │
  └───────────────┴───────────────────────┴────────────────┴──────────┘

  3 masters + 3 workers, all running RHCOS on Kubernetes v1.31.11. Everything looks healthy.

────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
❯ 
────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────




[.......
# Test 3 — Pods
"Show me pods in namespace openshift-monitoring"

..........]


❯ Show me pods in namespace openshift-monitoring

● Calling ocp-mcp… (ctrl+o to expand)

────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
 Tool use

   ocp-mcp - get_pods(namespace: "openshift-monitoring") (MCP)
   Get all pods and their status in a given namespace

 Do you want to proceed?
 ▒ Check OpenShift Container Platform login status
   2. Yes, and don't ask again for ocp-mcp - get_pods commands in /ocp-claude-skills
   3. No

 Esc to cancel · Tab to amend
 
 
 

❯ Show me pods in namespace openshift-monitoring

  Called ocp-mcp (ctrl+o to expand)

● All 23 pods in openshift-monitoring are Running with no issues:

  ┌──────────────────────────────────────────────┬──────────┬──────────┐
  │                     Pod                      │  Ready   │ Restarts │
  ├──────────────────────────────────────────────┼──────────┼──────────┤
  │ alertmanager-main-0                          │ 6/6      │ 12       │
  ├──────────────────────────────────────────────┼──────────┼──────────┤
  │ alertmanager-main-1                          │ 6/6      │ 18       │
  ├──────────────────────────────────────────────┼──────────┼──────────┤
  │ cluster-monitoring-operator-86d48cf768-mxttk │ 1/1      │ 1        │
  ├──────────────────────────────────────────────┼──────────┼──────────┤
  │ kube-state-metrics-57db8f7c58-rkc9s          │ 3/3      │ 9        │
  ├──────────────────────────────────────────────┼──────────┼──────────┤
  │ metrics-server-6f7bf886b5-rd8cc              │ 1/1      │ 0        │
  ├──────────────────────────────────────────────┼──────────┼──────────┤
  │ metrics-server-6f7bf886b5-wp6xn              │ 1/1      │ 0        │
  ├──────────────────────────────────────────────┼──────────┼──────────┤
  │ monitoring-plugin-9889797cb-6mrhq            │ 1/1      │ 2        │
  ├──────────────────────────────────────────────┼──────────┼──────────┤
  │ monitoring-plugin-9889797cb-rqxc5            │ 1/1      │ 3        │
  ├──────────────────────────────────────────────┼──────────┼──────────┤
  │ node-exporter-* (6 pods)                     │ 2/2 each │ —        │
  ├──────────────────────────────────────────────┼──────────┼──────────┤
  │ openshift-state-metrics-7867497d99-m4sfj     │ 3/3      │ 9        │
  ├──────────────────────────────────────────────┼──────────┼──────────┤
  │ prometheus-k8s-0                             │ 6/6      │ 18       │
  ├──────────────────────────────────────────────┼──────────┼──────────┤
  │ prometheus-k8s-1                             │ 6/6      │ 12       │
  ├──────────────────────────────────────────────┼──────────┼──────────┤
  │ prometheus-operator-6c944b95ff-w4s2m         │ 2/2      │ 2        │
  ├──────────────────────────────────────────────┼──────────┼──────────┤
  │ prometheus-operator-admission-webhook-* (2)  │ 1/1 each │ —        │
  ├──────────────────────────────────────────────┼──────────┼──────────┤
  │ telemeter-client-7c87bbb6fd-47hbk            │ 3/3      │ 6        │
  ├──────────────────────────────────────────────┼──────────┼──────────┤
  │ thanos-querier-b4f9584c-69dgk                │ 6/6      │ 18       │
  ├──────────────────────────────────────────────┼──────────┼──────────┤
  │ thanos-querier-b4f9584c-rdx9f                │ 6/6      │ 12       │
  └──────────────────────────────────────────────┴──────────┴──────────┘

  Everything is healthy. The restart counts are normal for long-running pods (205 days old).

─────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
❯ 
─────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
  ? for shortcuts

❯ exit
─────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────

Resume this session with:
claude --resume 4db7a943-5ffd-4227-9157-55c8d39a22be

Total cost:            $0.1104
Total duration (API):  30s
Total duration (wall): 18m 15s
Total code changes:    0 lines added, 0 lines removed
Usage by model:
    claude-haiku-4-5:  343 input, 16 output, 0 cache read, 0 cache write ($0.0004)
   claude-sonnet-4-6:  23 input, 1.4k output, 176.5k cache read, 9.4k cache write ($0.1100)


