---
title: "ASP.NET Core web アプリ用の推奨事項をホストしている azure"
description: "ASP.NET Core と Azure での最新の Web アプリケーションを設計 |ASP.NET web アプリ用の推奨事項をホストしている azure"
author: ardalis
ms.author: wiwagn
ms.date: 10/07/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.openlocfilehash: c361a28321ec9dcbfee1db8036757632a5d81f7c
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2017
---
# <a name="azure-hosting-recommendations-for-aspnet-core-web-apps"></a><span data-ttu-id="5c78e-103">ASP.NET Core Web アプリ用の推奨事項をホストしている azure</span><span class="sxs-lookup"><span data-stu-id="5c78e-103">Azure Hosting Recommendations for ASP.NET Core Web Apps</span></span>

> <span data-ttu-id="5c78e-104">"基幹業務リーダー everywhere がクラウド (別名 SaaS) からアプリケーションを取得すると共に、IT 部門のバイパスと支払いそれらの雑誌の講読と同じようにします。</span><span class="sxs-lookup"><span data-stu-id="5c78e-104">"Line-of-business leaders everywhere are bypassing IT departments to get applications from the cloud (aka SaaS) and paying for them like they would a magazine subscription.</span></span> <span data-ttu-id="5c78e-105">左上隅にある未使用ありません装置と、サブスクリプションを取り消すことができます、サービスが必要でなくなったときにします。"</span><span class="sxs-lookup"><span data-stu-id="5c78e-105">And when the service is no longer required, they can cancel the subscription with no equipment left unused in the corner."</span></span>  
> <span data-ttu-id="5c78e-106">_\-Daryl Plummer、Gartner アナリスト_</span><span class="sxs-lookup"><span data-stu-id="5c78e-106">_\- Daryl Plummer, Gartner analyst_</span></span>

## <a name="summary"></a><span data-ttu-id="5c78e-107">概要</span><span class="sxs-lookup"><span data-stu-id="5c78e-107">Summary</span></span>

<span data-ttu-id="5c78e-108">これは、アプリケーションのニーズとアーキテクチャ、Windows Azure でサポートできます。</span><span class="sxs-lookup"><span data-stu-id="5c78e-108">Whatever your application's needs and architecture, Windows Azure can support it.</span></span> <span data-ttu-id="5c78e-109">ホスティングのニーズは非常に高度なアプリケーション数十個サービスの構成に静的な web サイトと同じくらい簡単にできます。</span><span class="sxs-lookup"><span data-stu-id="5c78e-109">Your hosting needs can be as simple as a static web site to an extremely sophisticated application made up of dozens of services.</span></span> <span data-ttu-id="5c78e-110">ASP.NET Core モノリシックな web アプリケーションおよびサポート サービスでは、推奨されるいくつかのよく知られている構成があります。</span><span class="sxs-lookup"><span data-stu-id="5c78e-110">For ASP.NET Core monolithic web applications and supporting services, there are several well-known configurations that are recommended.</span></span> <span data-ttu-id="5c78e-111">次の推奨事項は、ホストされているかどうか完全なアプリケーション、個別のプロセス、またはデータをリソースの種類に従ってグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="5c78e-111">The recommendations below are grouped according to the kind of resource to be hosted, whether full applications, individual processes, or data.</span></span>

## <a name="web-applications"></a><span data-ttu-id="5c78e-112">Web アプリケーション</span><span class="sxs-lookup"><span data-stu-id="5c78e-112">Web Applications</span></span>

<span data-ttu-id="5c78e-113">Web アプリケーションをホストできます。</span><span class="sxs-lookup"><span data-stu-id="5c78e-113">Web applications can be hosted with:</span></span>

-   <span data-ttu-id="5c78e-114">App Service Web Apps</span><span class="sxs-lookup"><span data-stu-id="5c78e-114">App Service Web Apps</span></span>

-   <span data-ttu-id="5c78e-115">コンテナー</span><span class="sxs-lookup"><span data-stu-id="5c78e-115">Containers</span></span>

-   <span data-ttu-id="5c78e-116">Azure Service Fabric</span><span class="sxs-lookup"><span data-stu-id="5c78e-116">Azure Service Fabric</span></span>

-   <span data-ttu-id="5c78e-117">仮想マシン (Vm)</span><span class="sxs-lookup"><span data-stu-id="5c78e-117">Virtual Machines (VMs)</span></span>

<span data-ttu-id="5c78e-118">、App Service Web Apps はほとんどのシナリオの方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5c78e-118">Of these, App Service Web Apps are the recommended approach for most scenarios.</span></span> <span data-ttu-id="5c78e-119">マイクロ サービス アーキテクチャでは、コンテナー ベースのアプローチでは、またはサービス ファブリックを検討してください。</span><span class="sxs-lookup"><span data-stu-id="5c78e-119">For microservice architectures, consider a container-based approach, or service fabric.</span></span> <span data-ttu-id="5c78e-120">アプリケーションを実行しているマシンより詳細に制御を必要がある場合は、Azure の仮想マシンを検討してください。</span><span class="sxs-lookup"><span data-stu-id="5c78e-120">If you need more control over the machines running your application, consider Azure Virtual Machines.</span></span>

### <a name="app-service-web-apps"></a><span data-ttu-id="5c78e-121">App Service Web Apps</span><span class="sxs-lookup"><span data-stu-id="5c78e-121">App Service Web Apps</span></span>

<span data-ttu-id="5c78e-122">App Service Web Apps は、web アプリケーションをホストするために最適化された完全に管理されたプラットフォームを提供します。</span><span class="sxs-lookup"><span data-stu-id="5c78e-122">App Service Web Apps offers a fully managed platform optimized for hosting web applications.</span></span> <span data-ttu-id="5c78e-123">内容を実行し、アプリをスケールにより Azure インフラストラクチャの処理中に、ビジネス ロジックに集中することが必要である platform-as-a-service(PaaS) することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5c78e-123">It is a platform-as-a-service(PaaS) offering that lets you focus on your business logic, while Azure takes care of the infrastructure needed to run and scale the app.</span></span> <span data-ttu-id="5c78e-124">App Service Web Apps のいくつか主な機能:</span><span class="sxs-lookup"><span data-stu-id="5c78e-124">Some key features of App Service Web Apps:</span></span>

-   <span data-ttu-id="5c78e-125">DevOps の最適化 (継続的インテグレーションと配信、複数の環境では、A/テスト、スクリプトのサポート、B)</span><span class="sxs-lookup"><span data-stu-id="5c78e-125">DevOps optimization (continuous integration and delivery, multiple environments, A/B testing, scripting support)</span></span>

-   <span data-ttu-id="5c78e-126">グローバルの拡張性と高可用性</span><span class="sxs-lookup"><span data-stu-id="5c78e-126">Global scale and high availability</span></span>

-   <span data-ttu-id="5c78e-127">SaaS プラットフォームと、内部設置型データへの接続</span><span class="sxs-lookup"><span data-stu-id="5c78e-127">Connections to SaaS platforms and your on-premises data</span></span>

-   <span data-ttu-id="5c78e-128">セキュリティとコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="5c78e-128">Security and compliance</span></span>

-   <span data-ttu-id="5c78e-129">Visual Studio の統合環境</span><span class="sxs-lookup"><span data-stu-id="5c78e-129">Visual Studio integration</span></span>

<span data-ttu-id="5c78e-130">Azure App Service は、ほとんどの web アプリに最適な選択肢です。</span><span class="sxs-lookup"><span data-stu-id="5c78e-130">Azure App Service is the best choice for most web apps.</span></span> <span data-ttu-id="5c78e-131">展開と管理は、プラットフォームに統合されて、大量のトラフィックの負荷を処理するサイトをすばやくスケールできますおよび組み込みの負荷分散とトラフィック マネージャーは、高可用性を実現します。</span><span class="sxs-lookup"><span data-stu-id="5c78e-131">Deployment and management are integrated into the platform, sites can scale quickly to handle high traffic loads, and the built-in load balancing and traffic manager provide high availability.</span></span> <span data-ttu-id="5c78e-132">Azure App Service に簡単に、オンラインでの移行ツールを使用して既存のサイトのオープン ソース アプリケーションを使用して、Web アプリケーション ギャラリーから、またはフレームワークと任意のツールを使用して新しいサイトを作成を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5c78e-132">You can move existing sites to Azure App Service easily with an online migration tool, use an open-source app from the Web Application Gallery, or create a new site using the framework and tools of your choice.</span></span> <span data-ttu-id="5c78e-133">Web ジョブ機能により、簡単に App Service web アプリを処理するバック グラウンド ジョブを追加します。</span><span class="sxs-lookup"><span data-stu-id="5c78e-133">The WebJobs feature makes it easy to add background job processing to your App Service web app.</span></span>

### <a name="containers-and-azure-container-service"></a><span data-ttu-id="5c78e-134">コンテナーとコンテナーの Azure サービス</span><span class="sxs-lookup"><span data-stu-id="5c78e-134">Containers and Azure Container Service</span></span>

<span data-ttu-id="5c78e-135">Azure のコンテナー サービスが簡単にすると、作成、構成、およびコンテナー化アプリケーションを実行する事前に構成されている仮想マシンのクラスターを管理します。</span><span class="sxs-lookup"><span data-stu-id="5c78e-135">Azure Container Service makes it simpler for you to create, configure, and manage a cluster of virtual machines that are preconfigured to run containerized applications.</span></span> <span data-ttu-id="5c78e-136">一般的なオープン ソースのスケジュール設定およびオーケストレーションのツールの構成を最適化を使用します。</span><span class="sxs-lookup"><span data-stu-id="5c78e-136">It uses an optimized configuration of popular open-source scheduling and orchestration tools.</span></span> <span data-ttu-id="5c78e-137">これにより、既存のスキルを使用したり、Microsoft Azure でコンテナー ベースのアプリケーション展開および管理する、コミュニティの専門知識の発展し続けている本文に描画することができます。</span><span class="sxs-lookup"><span data-stu-id="5c78e-137">This enables you to use your existing skills, or draw upon a large and growing body of community expertise, to deploy and manage container-based applications on Microsoft Azure.</span></span>

<span data-ttu-id="5c78e-138">Azure のコンテナー サービスが簡単にすると、作成、構成、およびコンテナー化アプリケーションを実行する事前に構成されている仮想マシンのクラスターを管理します。</span><span class="sxs-lookup"><span data-stu-id="5c78e-138">Azure Container Service makes it simpler for you to create, configure, and manage a cluster of virtual machines that are preconfigured to run containerized applications.</span></span> <span data-ttu-id="5c78e-139">一般的なオープン ソースのスケジュール設定およびオーケストレーションのツールの構成を最適化を使用します。</span><span class="sxs-lookup"><span data-stu-id="5c78e-139">It uses an optimized configuration of popular open-source scheduling and orchestration tools.</span></span> <span data-ttu-id="5c78e-140">これにより、既存のスキルを使用したり、Microsoft Azure でコンテナー ベースのアプリケーション展開および管理する、コミュニティの専門知識の発展し続けている本文に描画することができます。</span><span class="sxs-lookup"><span data-stu-id="5c78e-140">This enables you to use your existing skills, or draw upon a large and growing body of community expertise, to deploy and manage container-based applications on Microsoft Azure.</span></span>

<span data-ttu-id="5c78e-141">Azure コンテナー サービスの 1 つの目標は、今日はマイクロソフトのお客様の間でよく使用するオープン ソース ツールとテクノロジを使用して、コンテナー ホスト環境を提供します。</span><span class="sxs-lookup"><span data-stu-id="5c78e-141">One goal of Azure Container Service is to provide a container hosting environment using open-source tools and technologies that are popular among Microsoft's customers today.</span></span> <span data-ttu-id="5c78e-142">この end には、Azure コンテナー サービスは、(DC/OS、Docker Swarm、または Kubernetes)、選択した orchestrator の標準 API エンドポイントを公開します。</span><span class="sxs-lookup"><span data-stu-id="5c78e-142">To this end, Azure Container Service exposes the standard API endpoints for your chosen orchestrator (DC/OS, Docker Swarm, or Kubernetes).</span></span> <span data-ttu-id="5c78e-143">これらのエンドポイントを使用すると、それらのエンドポイントと通信できる任意のソフトウェアを利用できます。</span><span class="sxs-lookup"><span data-stu-id="5c78e-143">By using these endpoints, you can leverage any software that is capable of talking to those endpoints.</span></span> <span data-ttu-id="5c78e-144">たとえばの場合は、Docker Swarm エンドポイントすることもできます Docker コマンド ライン インターフェイス (CLI) を使用します。</span><span class="sxs-lookup"><span data-stu-id="5c78e-144">For example, in the case of the Docker Swarm endpoint, you might choose to use the Docker command-line interface (CLI).</span></span> <span data-ttu-id="5c78e-145">DC/OS DCOS CLI を選択できます。</span><span class="sxs-lookup"><span data-stu-id="5c78e-145">For DC/OS, you might choose the DCOS CLI.</span></span> <span data-ttu-id="5c78e-146">Kubernetes、kubectl を選択できます。</span><span class="sxs-lookup"><span data-stu-id="5c78e-146">For Kubernetes, you might choose kubectl.</span></span> <span data-ttu-id="5c78e-147">図 11-1 では、コンテナー、クラスターを管理するこれらのエンドポイントを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5c78e-147">Figure 11-1 shows how you would use these endpoints to manage your container clusters.</span></span>

![](./media/image11-1.png)

<span data-ttu-id="5c78e-148">**図 11-1。**</span><span class="sxs-lookup"><span data-stu-id="5c78e-148">**Figure 11-1.**</span></span> <span data-ttu-id="5c78e-149">Docker、Kubernetes、または DC/OS エンドポイントで azure のコンテナー サービスの管理。</span><span class="sxs-lookup"><span data-stu-id="5c78e-149">Azure Container Service management with Docker, Kubernetes, or DC/OS endpoints.</span></span>

### <a name="azure-service-fabric"></a><span data-ttu-id="5c78e-150">Azure Service Fabric</span><span class="sxs-lookup"><span data-stu-id="5c78e-150">Azure Service Fabric</span></span>

<span data-ttu-id="5c78e-151">Service Fabric は、新しいアプリの作成または再マイクロ サービス アーキテクチャを使用する既存のアプリを記述する場合、適切な選択です。</span><span class="sxs-lookup"><span data-stu-id="5c78e-151">Service Fabric is a good choice if you're creating a new app or re-writing an existing app to use a microservice architecture.</span></span> <span data-ttu-id="5c78e-152">マシンの共有プールで実行すると、アプリでは、小さな開始でき、数百または数千の必要に応じてマシンでの大規模なスケールに拡大することができます。</span><span class="sxs-lookup"><span data-stu-id="5c78e-152">Apps, which run on a shared pool of machines, can start small and grow to massive scale with hundreds or thousands of machines as needed.</span></span> <span data-ttu-id="5c78e-153">ステートフルなサービスしやすい一貫したと確実には、アプリの状態を格納し、Service Fabric はサービスがパーティション分割、スケール、および可用性を自動的に管理するとします。</span><span class="sxs-lookup"><span data-stu-id="5c78e-153">Stateful services make it easy to consistently and reliably store app state, and Service Fabric automatically manages service partitioning, scaling, and availability for you.</span></span> <span data-ttu-id="5c78e-154">Service Fabric には、.NET (OWIN) および ASP.NET Core の Open Web Interface と WebAPI もサポートしています。</span><span class="sxs-lookup"><span data-stu-id="5c78e-154">Service Fabric also supports WebAPI with Open Web Interface for .NET (OWIN) and ASP.NET Core.</span></span> <span data-ttu-id="5c78e-155">App Service と比較して、Service Fabric も提供以上の制御、または基になるインフラストラクチャに直接アクセスします。</span><span class="sxs-lookup"><span data-stu-id="5c78e-155">Compared to App Service, Service Fabric also provides more control over, or direct access to, the underlying infrastructure.</span></span> <span data-ttu-id="5c78e-156">リモート サーバーにしたり、サーバーのスタートアップ タスクを構成できます。</span><span class="sxs-lookup"><span data-stu-id="5c78e-156">You can remote into your servers or configure server startup tasks.</span></span>

### <a name="azure-virtual-machines"></a><span data-ttu-id="5c78e-157">Azure Virtual Machines</span><span class="sxs-lookup"><span data-stu-id="5c78e-157">Azure Virtual Machines</span></span>

<span data-ttu-id="5c78e-158">App Service または Service Fabric で実行するの大幅な変更が必要となる既存のアプリケーションがあれば、クラウドへの移行を簡素化するために仮想マシンを選択できます。</span><span class="sxs-lookup"><span data-stu-id="5c78e-158">If you have an existing application that would require substantial modifications to run in App Service or Service Fabric, you could choose Virtual Machines in order to simplify migrating to the cloud.</span></span> <span data-ttu-id="5c78e-159">ただし、正しく構成、セキュリティ、および保守 Vm が必要です、さまざまな時間と Azure App Service と Service Fabric と比較して IT の専門知識。</span><span class="sxs-lookup"><span data-stu-id="5c78e-159">However, correctly configuring, securing, and maintaining VMs requires much more time and IT expertise compared to Azure App Service and Service Fabric.</span></span> <span data-ttu-id="5c78e-160">Azure の仮想マシンを検討している場合は、考慮する修正プログラム、更新、および VM 環境の管理に必要な継続的なメンテナンス作業を確認します。</span><span class="sxs-lookup"><span data-stu-id="5c78e-160">If you are considering Azure Virtual Machines, make sure you take into account the ongoing maintenance effort required to patch, update, and manage your VM environment.</span></span> <span data-ttu-id="5c78e-161">Azure の仮想マシンは、App Service と Service Fabric プラットフォーム-as a Service (Paas) されているときにインフラストラクチャ-as a Service (IaaS) がします。</span><span class="sxs-lookup"><span data-stu-id="5c78e-161">Azure Virtual Machines is Infrastructure-as-a-Service (IaaS), while App Service and Service Fabric are Platform-as-a-Service (Paas).</span></span>

#### <a name="feature-comparison"></a><span data-ttu-id="5c78e-162">機能の比較</span><span class="sxs-lookup"><span data-stu-id="5c78e-162">Feature Comparison</span></span>

| <span data-ttu-id="5c78e-163">App Service を機能します。</span><span class="sxs-lookup"><span data-stu-id="5c78e-163">Feature App Service</span></span> | <span data-ttu-id="5c78e-164">Service Fabric</span><span class="sxs-lookup"><span data-stu-id="5c78e-164">Service Fabric</span></span> | <span data-ttu-id="5c78e-165">仮想マシン</span><span class="sxs-lookup"><span data-stu-id="5c78e-165">Virtual Machine</span></span> |
|---------|----------|----------|
| <span data-ttu-id="5c78e-166">ほぼ即時の配置</span><span class="sxs-lookup"><span data-stu-id="5c78e-166">Near-Instant Deployment</span></span> | <span data-ttu-id="5c78e-167">X</span><span class="sxs-lookup"><span data-stu-id="5c78e-167">X</span></span> | <span data-ttu-id="5c78e-168">X</span><span class="sxs-lookup"><span data-stu-id="5c78e-168">X</span></span> | |
| <span data-ttu-id="5c78e-169">再配置することがなく大型のコンピューターにスケール アップ</span><span class="sxs-lookup"><span data-stu-id="5c78e-169">Scale up to larger machines without redeploy</span></span> | <span data-ttu-id="5c78e-170">X</span><span class="sxs-lookup"><span data-stu-id="5c78e-170">X</span></span> | <span data-ttu-id="5c78e-171">X</span><span class="sxs-lookup"><span data-stu-id="5c78e-171">X</span></span> | |
| <span data-ttu-id="5c78e-172">インスタンスを共有コンテンツと構成です。再展開または拡張するときに再構成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="5c78e-172">Instances share content and configuration; no need to redeploy or reconfigure when scaling</span></span> | <span data-ttu-id="5c78e-173">X</span><span class="sxs-lookup"><span data-stu-id="5c78e-173">X</span></span> | <span data-ttu-id="5c78e-174">X</span><span class="sxs-lookup"><span data-stu-id="5c78e-174">X</span></span> | |
| <span data-ttu-id="5c78e-175">複数のデプロイ環境 (運用環境、ステージング)</span><span class="sxs-lookup"><span data-stu-id="5c78e-175">Multiple deployment environments (production, staging)</span></span> | <span data-ttu-id="5c78e-176">X</span><span class="sxs-lookup"><span data-stu-id="5c78e-176">X</span></span> | <span data-ttu-id="5c78e-177">X</span><span class="sxs-lookup"><span data-stu-id="5c78e-177">X</span></span> | |
| <span data-ttu-id="5c78e-178">OS の自動更新の管理</span><span class="sxs-lookup"><span data-stu-id="5c78e-178">Automatic OS update management</span></span> | <span data-ttu-id="5c78e-179">X</span><span class="sxs-lookup"><span data-stu-id="5c78e-179">X</span></span> | | |
| <span data-ttu-id="5c78e-180">シームレスな 32/64 ビットのプラットフォーム間の切り替え</span><span class="sxs-lookup"><span data-stu-id="5c78e-180">Seamless switching between 32/64 bit platforms</span></span> | <span data-ttu-id="5c78e-181">X</span><span class="sxs-lookup"><span data-stu-id="5c78e-181">X</span></span> | | |
| <span data-ttu-id="5c78e-182">Git、FTP によるコードを配置します。</span><span class="sxs-lookup"><span data-stu-id="5c78e-182">Deploy code with Git, FTP</span></span> | <span data-ttu-id="5c78e-183">X</span><span class="sxs-lookup"><span data-stu-id="5c78e-183">X</span></span> | | <span data-ttu-id="5c78e-184">X</span><span class="sxs-lookup"><span data-stu-id="5c78e-184">X</span></span> |
| <span data-ttu-id="5c78e-185">Web Deploy によるコードを配置します。</span><span class="sxs-lookup"><span data-stu-id="5c78e-185">Deploy code with WebDeploy</span></span> | <span data-ttu-id="5c78e-186">X</span><span class="sxs-lookup"><span data-stu-id="5c78e-186">X</span></span> | | <span data-ttu-id="5c78e-187">X</span><span class="sxs-lookup"><span data-stu-id="5c78e-187">X</span></span> |
| <span data-ttu-id="5c78e-188">TFS によるコードを配置します。</span><span class="sxs-lookup"><span data-stu-id="5c78e-188">Deploy code with TFS</span></span> | <span data-ttu-id="5c78e-189">X</span><span class="sxs-lookup"><span data-stu-id="5c78e-189">X</span></span> | <span data-ttu-id="5c78e-190">X</span><span class="sxs-lookup"><span data-stu-id="5c78e-190">X</span></span> | <span data-ttu-id="5c78e-191">X</span><span class="sxs-lookup"><span data-stu-id="5c78e-191">X</span></span> |
| <span data-ttu-id="5c78e-192">ホスト web または多層アーキテクチャの web サービス層</span><span class="sxs-lookup"><span data-stu-id="5c78e-192">Host web or web service tier of multi-tier architecture</span></span> | <span data-ttu-id="5c78e-193">X</span><span class="sxs-lookup"><span data-stu-id="5c78e-193">X</span></span> | <span data-ttu-id="5c78e-194">X</span><span class="sxs-lookup"><span data-stu-id="5c78e-194">X</span></span> | <span data-ttu-id="5c78e-195">X</span><span class="sxs-lookup"><span data-stu-id="5c78e-195">X</span></span> |
| <span data-ttu-id="5c78e-196">Service Bus、Storage、SQL データベースのような Azure サービスへのアクセスします。</span><span class="sxs-lookup"><span data-stu-id="5c78e-196">Access Azure services like Service Bus, Storage, SQL Database</span></span> | <span data-ttu-id="5c78e-197">X</span><span class="sxs-lookup"><span data-stu-id="5c78e-197">X</span></span> | <span data-ttu-id="5c78e-198">X</span><span class="sxs-lookup"><span data-stu-id="5c78e-198">X</span></span> | <span data-ttu-id="5c78e-199">X</span><span class="sxs-lookup"><span data-stu-id="5c78e-199">X</span></span> |
| <span data-ttu-id="5c78e-200">任意のカスタム MSI をインストールします。</span><span class="sxs-lookup"><span data-stu-id="5c78e-200">Install any custom MSI</span></span> | | <span data-ttu-id="5c78e-201">X</span><span class="sxs-lookup"><span data-stu-id="5c78e-201">X</span></span> | <span data-ttu-id="5c78e-202">X</span><span class="sxs-lookup"><span data-stu-id="5c78e-202">X</span></span> |

## <a name="logical-processes"></a><span data-ttu-id="5c78e-203">論理プロセス</span><span class="sxs-lookup"><span data-stu-id="5c78e-203">Logical Processes</span></span>

<span data-ttu-id="5c78e-204">個々 の論理プロセスで、アプリケーションの残りの部分から切り離すことができます展開することがない個別に Azure 関数「なし」のようにします。</span><span class="sxs-lookup"><span data-stu-id="5c78e-204">Individual logical processes that can be decoupled from the rest of the application may be deployed independently to Azure Functions in a "serverless" manner.</span></span> <span data-ttu-id="5c78e-205">Azure 機能では、特定の問題について、それを実行するアプリケーションまたはインフラストラクチャを気にせず、必要なコードを書き込むだけことができます。</span><span class="sxs-lookup"><span data-stu-id="5c78e-205">Azure Functions lets you just write the code you need for a given problem, without worrying about the application or infrastructure to run it.</span></span> <span data-ttu-id="5c78e-206">さまざまな C などのプログラミング言語から選択できる\#、F\#Node.js、Python、PHP、当面タスクの生産性のほとんどの言語を選択することができます。</span><span class="sxs-lookup"><span data-stu-id="5c78e-206">You can choose from a variety of programming languages, including C\#, F\#, Node.js, Python, and PHP, allowing you to pick the most productive language for the task at hand.</span></span> <span data-ttu-id="5c78e-207">ほとんどのクラウド ベースのソリューションと同様に、使用時間分だけ支払うおよび必要に応じてスケール アップする Azure 機能を信頼することができます。</span><span class="sxs-lookup"><span data-stu-id="5c78e-207">Like most cloud-based solutions, you pay only for the amount of time your use, and you can trust Azure Functions to scale up as needed.</span></span>

## <a name="data"></a><span data-ttu-id="5c78e-208">データ</span><span class="sxs-lookup"><span data-stu-id="5c78e-208">Data</span></span>

<span data-ttu-id="5c78e-209">Azure は、アプリケーションは、該当するデータの適切なデータ プロバイダーを使用できるように、さまざまなデータ記憶域オプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="5c78e-209">Azure offers a wide variety of data storage options, so that your application can use the appropriate data provider for the data in question.</span></span>

<span data-ttu-id="5c78e-210">トランザクション、リレーショナル データの場合は、Azure SQL データベースは、最適なオプションです。</span><span class="sxs-lookup"><span data-stu-id="5c78e-210">For transactional, relational data, Azure SQL Databases are the best option.</span></span> <span data-ttu-id="5c78e-211">高パフォーマンス通常は読み取り専用データ、Azure SQL データベースでバックアップ Redis cache は良いソリューションです。</span><span class="sxs-lookup"><span data-stu-id="5c78e-211">For high performance read-mostly data, a Redis cache backed by an Azure SQL Database is a good solution.</span></span>

<span data-ttu-id="5c78e-212">さまざまな DocumentDB に Blob または Azure ストレージ内のテーブルに列を SQL データベースからの方法では、JSON の非構造化データを格納できます。</span><span class="sxs-lookup"><span data-stu-id="5c78e-212">Unstructured JSON data can be stored in a variety of ways, from SQL Database columns to Blobs or Tables in Azure Storage, to DocumentDB.</span></span> <span data-ttu-id="5c78e-213">これらのうち、DocumentDB 最適なクエリ機能を提供しています、大量のクエリをサポートする必要がある JSON ベースのドキュメントに推奨されるオプション。</span><span class="sxs-lookup"><span data-stu-id="5c78e-213">Of these, DocumentDB offers the best querying functionality, and is the recommended option for large numbers of JSON-based documents that must support querying.</span></span>

<span data-ttu-id="5c78e-214">アプリケーションの動作を調整するために使用される一時的なコマンドまたはイベント ベースのデータには、Azure Service Bus または Azure ストレージ キューを使用できます。</span><span class="sxs-lookup"><span data-stu-id="5c78e-214">Transient command- or event-based data used to orchestrate application behavior can use Azure Service Bus or Azure Storage Queues.</span></span> <span data-ttu-id="5c78e-215">Azure の記憶域バスも高い柔軟性し、内およびアプリケーション間では、重要なメッセージングのための推奨されるサービスです。</span><span class="sxs-lookup"><span data-stu-id="5c78e-215">Azure Storage Bus offers more flexibility and is the recommended service for non-trivial messaging within and between applications.</span></span>

## <a name="architecture-recommendations"></a><span data-ttu-id="5c78e-216">アーキテクチャの推奨事項</span><span class="sxs-lookup"><span data-stu-id="5c78e-216">Architecture Recommendations</span></span>

<span data-ttu-id="5c78e-217">アプリケーションの要件が、アーキテクチャを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c78e-217">Your application's requirements should dictate its architecture.</span></span> <span data-ttu-id="5c78e-218">多くのさまざまな Azure サービスが利用可能な重要な判断を右側の 1 つを選択します。</span><span class="sxs-lookup"><span data-stu-id="5c78e-218">There are many different Azure services available, choosing the right one is an important decision.</span></span> <span data-ttu-id="5c78e-219">Microsoft では、一般的なシナリオ用に最適化された一般的なアーキテクチャを識別できるように参照アーキテクチャのギャラリーを提供します。</span><span class="sxs-lookup"><span data-stu-id="5c78e-219">Microsoft offers a gallery of reference architectures to help identify typical architectures optimized for common scenarios.</span></span> <span data-ttu-id="5c78e-220">マップ、アプリケーションの要件に最も近いまたは少なくとも開始点が用意されている参照アーキテクチャをバインドすることがあります。</span><span class="sxs-lookup"><span data-stu-id="5c78e-220">You may bind a reference architecture that maps closely to your application's requirements, or at least offers a starting point.</span></span>

<span data-ttu-id="5c78e-221">図 11-2 では、参照アーキテクチャの例を示します。</span><span class="sxs-lookup"><span data-stu-id="5c78e-221">Figure 11-2 shows an example reference architecture.</span></span> <span data-ttu-id="5c78e-222">この図では、marketing 用に最適化された Sitecore コンテンツ管理システム web サイトの推奨アーキテクチャ アプローチについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5c78e-222">This diagram describes a recommended architecture approach for a Sitecore content management system website optimized for marketing.</span></span>

![](./media/image11-2.png)

<span data-ttu-id="5c78e-223">**図 11-2 です。**</span><span class="sxs-lookup"><span data-stu-id="5c78e-223">**Figure 11-2.**</span></span> <span data-ttu-id="5c78e-224">Web サイトの参照アーキテクチャのマーケティング Sitecore です。</span><span class="sxs-lookup"><span data-stu-id="5c78e-224">Sitecore marketing website reference architecture.</span></span>

<span data-ttu-id="5c78e-225">**– Azure の推奨事項をホスティングの参照**</span><span class="sxs-lookup"><span data-stu-id="5c78e-225">**References – Azure Hosting Recommendations**</span></span>

-   <span data-ttu-id="5c78e-226">Azure ソリューション Architectures\\</span><span class="sxs-lookup"><span data-stu-id="5c78e-226">Azure Solution Architectures\\</span></span>
    <span data-ttu-id="5c78e-227"><https://azure.microsoft.com/solutions/architecture/></span><span class="sxs-lookup"><span data-stu-id="5c78e-227"><https://azure.microsoft.com/solutions/architecture/></span></span>

-   <span data-ttu-id="5c78e-228">Azure 開発者 Guide\\</span><span class="sxs-lookup"><span data-stu-id="5c78e-228">Azure Developer Guide\\</span></span>
    <span data-ttu-id="5c78e-229"><https://azure.microsoft.com/campaigns/developer-guide/></span><span class="sxs-lookup"><span data-stu-id="5c78e-229"><https://azure.microsoft.com/campaigns/developer-guide/></span></span>

-   <span data-ttu-id="5c78e-230">Azure App Service は何ですか? \\</span><span class="sxs-lookup"><span data-stu-id="5c78e-230">What is Azure App Service?\\</span></span>
    <span data-ttu-id="5c78e-231"><https://docs.microsoft.com/azure/app-service/app-service-value-prop-what-is></span><span class="sxs-lookup"><span data-stu-id="5c78e-231"><https://docs.microsoft.com/azure/app-service/app-service-value-prop-what-is></span></span>

-   <span data-ttu-id="5c78e-232">Azure App Service、仮想マシン、Service Fabric およびクラウド サービスの比較 \\</span><span class="sxs-lookup"><span data-stu-id="5c78e-232">Azure App Service, Virtual Machines, Service Fabric and Cloud Services Comparison\\</span></span>
    <span data-ttu-id="5c78e-233"><https://docs.microsoft.com/azure/app-service-web/choose-web-site-cloud-service-vm></span><span class="sxs-lookup"><span data-stu-id="5c78e-233"><https://docs.microsoft.com/azure/app-service-web/choose-web-site-cloud-service-vm></span></span>

>[!div class="step-by-step"]
<span data-ttu-id="5c78e-234">[前](開発のプロセス-の-azure.md)</span><span class="sxs-lookup"><span data-stu-id="5c78e-234">[Previous] (development-process-for-azure.md)</span></span>