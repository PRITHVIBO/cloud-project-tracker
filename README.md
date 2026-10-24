# CloudLab — Cloud Computing & DevOps Project Tracker

CloudLab is a responsive, dependency-free learning tracker for discovering reference repositories, comparing cloud deployment options, and tracking your own builds from first run to a deployed portfolio project.

## What's new in this version

- **179 curated starter records** spanning AWS, Azure, Google Cloud, Oracle Cloud Infrastructure (OCI), Cloudflare Workers, Render, Kubernetes, DevOps/CI/CD, DigitalOcean, Vercel, Netlify, Railway, Fly.io, Heroku, IBM Cloud, Hetzner Cloud, Alibaba Cloud, Supabase, Firebase, Appwrite, Vultr, Akamai Cloud/Linode, OVHcloud, Scaleway, Tencent Cloud, Huawei Cloud, Backblaze, Deno Deploy, and Fastly.
- **Live GitHub discovery:** click **Live GitHub search** to query the public GitHub Search API. Results include repository description, stars, language, topics, and last-push/update date where GitHub provides them. You can add a result to your library and learning plan.
- **Safer source labeling:** entries from provider/maintainer organizations are labeled separately from ordinary community repos. Demo URLs are not treated as guaranteed live; open them and check availability yourself.
- **Separate reference and personal URLs:** save the original repo you are learning from, your own GitHub repo, your deployed website/demo, and the tutorial/deployment guide as separate fields.
- **Preserved progress during catalog updates:** on startup, the app merges new curated projects into existing browser data while preserving saved progress and personal projects. Deleting a curated project stores a local tombstone so it stays hidden after reload.
- **Learning workflow:** mark projects Not started / In progress / Completed and check off reading docs/license, running locally, modifying a feature, deploying your version, and documenting architecture/cost/security.
- Search/filter by cloud platform, project type/category, difficulty, status, tags and keywords; quick live-search presets for IaC, Kubernetes, serverless, CI/CD, monitoring, security, backup/disaster recovery, FinOps, migration, edge/CDN and data engineering; roadmap, JSON export/import, and responsive layouts.

## Run locally

1. Extract `cloud-project-tracker.zip`.
2. Open `index.html` in a modern browser.
3. For a normal local web origin, run a server from this folder:

   ```bash
   python -m http.server 8000
   ```

4. Open `http://localhost:8000`.

You can open the file directly for the curated catalog; the live GitHub search requires internet access and may work more reliably when served over localhost or HTTPS.

## Publish on GitHub Pages

1. Create a repository, for example `cloudlab-project-tracker`.
2. Upload `index.html` and `README.md` to its root.
3. Open **Settings → Pages**.
4. Choose **Deploy from a branch**, select the default branch (usually `main`) and `/ (root)`, then save.
5. Open the URL shown in the Pages settings.

No build step or API key is required.

## Live GitHub search reliability notes

Live discovery calls the unauthenticated public endpoint `https://api.github.com/search/repositories`. GitHub applies request limits; when the limit is reached, wait and retry or use the curated catalog. Search results are filtered to exclude archived repositories and forks, sorted by recent update, and limited to twenty per request. This is a discovery helper, not a security audit. A recent update or high star count does not prove that a project is safe, maintained to your standards, or compatible with current cloud service versions.

The curated catalog is embedded in `index.html`, so its starter records do not automatically refresh in the background. It is intentionally not claimed to contain every public cloud repository—GitHub has millions of changing repositories, and many are forks, tutorials or abandoned projects. Use the live GitHub search and the source directories below for ongoing discovery. To discover newer projects, use **Live GitHub search**. The app does not continuously ping or uptime-monitor demos. For project repositories, review the README, license, recent commits, issues/advisories, dependencies, required permissions and cloud pricing before deploying.

## Cloud cost and security checklist

- Create a budget alert before creating billable cloud resources.
- Review permissions and use least-privilege IAM/service identities.
- Never commit access keys, private keys, tokens or `.env` files.
- Check region availability, free-tier eligibility, quotas and estimated cost.
- Identify teardown instructions before deploying; delete billable resources when finished.
- Test backup restoration when the project stores data.
- Save screenshots, a concise architecture diagram, deployment steps, and a cost/security note in your own repository.

## Data and privacy

Project records are stored in browser `localStorage` on the current browser/profile and device. There is no login, database, or automatic cloud sync. Use **Export backup** before clearing site data or moving to another device. **Import** replaces the existing local tracker contents after confirmation. The GitHub search feature sends search terms to GitHub's public API; your personal project notes remain local unless you put them in a public repository or exported file.

## Seed catalogue — useful source organizations

- AWS samples and labs: <https://github.com/aws-samples>, <https://github.com/awslabs>
- Microsoft Azure samples and templates: <https://github.com/Azure-Samples>, <https://github.com/Azure/azure-quickstart-templates>
- Google Cloud samples: <https://github.com/GoogleCloudPlatform>
- Oracle Cloud Infrastructure samples: <https://github.com/oracle-devrel>
- Cloudflare Workers: <https://github.com/cloudflare/templates>, <https://github.com/cloudflare/python-workers-examples>
- Render examples: <https://github.com/render-examples>
- GitOps and CI/CD: <https://github.com/jenkinsci/pipeline-examples>, <https://github.com/argoproj/argo-cd>, <https://github.com/actions/starter-workflows>
- Terraform and cloud IaC: <https://github.com/hashicorp/terraform-guides>, <https://github.com/pulumi/examples>
- Additional providers: <https://github.com/digitalocean/kubernetes-sample-apps>, <https://github.com/vercel/examples>, <https://github.com/netlify-templates>, <https://github.com/railwayapp/templates>, <https://github.com/fly-apps>, <https://github.com/heroku>, <https://github.com/IBM-Cloud>, <https://github.com/hetznercloud>, <https://github.com/aliyun>, <https://github.com/alibabacloud-labs>, <https://github.com/supabase>, <https://github.com/firebase>, <https://github.com/appwrite>, <https://github.com/vultr>, <https://github.com/linode>, <https://github.com/ovh>, <https://github.com/scaleway>, <https://github.com/TencentCloud>, <https://github.com/huaweicloud>, <https://github.com/Backblaze>, <https://github.com/denoland>, <https://github.com/fastly>
- Cloud engineering tooling: <https://github.com/argoproj/argo-cd>, <https://github.com/fluxcd/flux2>, <https://github.com/crossplane/crossplane>, <https://github.com/open-telemetry/opentelemetry-demo>, <https://github.com/opencost/opencost>, <https://github.com/infracost/infracost>, <https://github.com/aquasecurity/trivy>, <https://github.com/grafana/helm-charts>

## Deployment responsibility

CloudLab is a tracker and discovery UI; it does not provision infrastructure by itself. Follow each provider's current documentation and review licensing/security before using a repository in production.
