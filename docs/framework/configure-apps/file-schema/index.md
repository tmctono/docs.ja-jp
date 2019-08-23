---
title: .NET Framework の構成ファイル スキーマ
ms.date: 05/01/2017
helpviewer_keywords:
- .NET Framework application configuration, configuration schema
- machine configuration files
- application configuration files, schema
- app.config files, schema
- schema configuration settings
- schemas, configuration settings
- enterprisesec.config files
- well-formed XML
- enterprisesec configuration files
- security.config files
- security [.NET Framework], configuration files
- application development [.NET Framework], schema
- XML tags
- container tags
- machine.config files
- configuration schema [.NET Framework]
- configuration settings [.NET Framework], applications
- configuration file reference [.NET Framework]
ms.assetid: 69003d39-dc8a-460c-a6be-e6d93e690b38
ms.openlocfilehash: c3b5518b4b86c2e6f47825d552f49579c5ac0a6d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921023"
---
# <a name="configuration-file-schema-for-the-net-framework"></a><span data-ttu-id="14491-102">.NET Framework の構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="14491-102">Configuration file schema for the .NET Framework</span></span>

<span data-ttu-id="14491-103">構成ファイルは、設定を変更し、アプリのポリシーを設定するために使用できる標準 XML ファイルです。</span><span class="sxs-lookup"><span data-stu-id="14491-103">Configuration files are standard XML files that you can use to change settings and set policies for your apps.</span></span> <span data-ttu-id="14491-104">.NET Framework の構成スキーマは、アプリの動作を制御するために構成ファイルで使用できる要素で構成されます。</span><span class="sxs-lookup"><span data-stu-id="14491-104">The .NET Framework configuration schema consists of elements that you can use in configuration files to control the behavior of your apps.</span></span> <span data-ttu-id="14491-105">このセクションの目次は、スキーマ、起動時の階層、ランタイム、ネットワーク、およびその他の種類の構成設定を反映しています。</span><span class="sxs-lookup"><span data-stu-id="14491-105">The table of contents for this section reflects the schema hierarchy for startup, runtime, network, and other types of configuration settings.</span></span>

<span data-ttu-id="14491-106">構成ファイルの種類、形式、および場所については、「[アプリの構成](../index.md)」の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14491-106">For information about the types, format, and location of configuration files, see the article [Configuring Apps](../index.md).</span></span> <span data-ttu-id="14491-107">構成ファイルを直接編集する場合は、XML に関する知識が必要です。</span><span class="sxs-lookup"><span data-stu-id="14491-107">Familiarize yourself with XML if you want to edit the configuration files directly.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="14491-108">構成ファイルの XML タグおよび属性では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="14491-108">XML tags and attributes in configuration files are case-sensitive.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="14491-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="14491-109">In this section</span></span>

<span data-ttu-id="14491-110">[ **\<configuration>** 要素](configuration-element.md) すべての構成ファイルの最上位要素である `<configuration>` 要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="14491-110">[**\<configuration>** Element](configuration-element.md) Describes the `<configuration>` element, which is the top-level element for all configuration files.</span></span>

<span data-ttu-id="14491-111">[ **\<assemblyBinding>** 要素](assemblybinding-element-for-configuration.md) 構成レベルでのアセンブリ バインディング ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="14491-111">[**\<assemblyBinding>** Element](assemblybinding-element-for-configuration.md) Specifies assembly binding policy at the configuration level.</span></span>

<span data-ttu-id="14491-112">[ **\<linkedConfiguration>** 要素](linkedconfiguration-element.md) インクルードする構成ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="14491-112">[**\<linkedConfiguration>** Element](linkedconfiguration-element.md) Specifies a configuration file to include.</span></span>

<span data-ttu-id="14491-113">[スタートアップ設定スキーマ](./startup/index.md) 使用する共通言語ランタイムのバージョンを指定する要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="14491-113">[Startup Settings Schema](./startup/index.md) Describes the elements that specify which version of the common language runtime to use.</span></span>

<span data-ttu-id="14491-114">[ランタイム設定スキーマ](./runtime/index.md) アセンブリのバインディングとランタイムの動作を構成する要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="14491-114">[Runtime Settings Schema](./runtime/index.md) Describes the elements that configure assembly binding and runtime behavior.</span></span>

<span data-ttu-id="14491-115">[ネットワーク設定スキーマ](./network/index.md) .NET Framework がインターネットに接続する方法を指定する要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="14491-115">[Network Settings Schema](./network/index.md) Describes the elements that specify how the .NET Framework connects to the Internet.</span></span>

<span data-ttu-id="14491-116">[暗号設定スキーマ](./cryptography/index.md) アルゴリズムの表示名を、暗号化アルゴリズムを実装するクラスに割り当てる要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="14491-116">[Cryptography Settings Schema](./cryptography/index.md) Describes elements that map friendly algorithm names to classes that implement cryptography algorithms.</span></span>

<span data-ttu-id="14491-117">[構成セクション スキーマ](configuration-sections-schema.md) カスタム設定の構成セクションを作成し、使用するための要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="14491-117">[Configuration Sections Schema](configuration-sections-schema.md) Describes the elements used to create and use configuration sections for custom settings.</span></span>

<span data-ttu-id="14491-118">[トレースおよびデバッグ設定のスキーマ](./trace-debug/index.md) トレース スイッチとリスナーを指定する要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="14491-118">[Trace and Debug Settings Schema](./trace-debug/index.md) Describes the elements that specify trace switches and listeners.</span></span>

<span data-ttu-id="14491-119">[コンパイラおよび言語プロバイダー設定のスキーマ](./compiler/index.md) 使用できる言語プロバイダーのコンパイラの構成を指定する要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="14491-119">[Compiler and Language Provider Settings Schema](./compiler/index.md) Describes the elements that specify compiler configuration for available language providers.</span></span>

<span data-ttu-id="14491-120">[アプリケーション設定のスキーマ](application-settings-schema.md) Windows フォームや ASP.NET アプリケーションで、アプリケーション スコープおよびユーザー スコープの設定の格納と取得を可能にする要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="14491-120">[Application Settings Schema](application-settings-schema.md) Describes the elements that enable a Windows Forms or ASP.NET application to store and retrieve application-scoped and user-scoped settings.</span></span>

<span data-ttu-id="14491-121">[アプリ設定スキーマ](./appsettings/index.md) ファイル パス、XML Web サービス URL、またはアプリケーションのその他のカスタム構成情報など、カスタム アプリケーションの設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="14491-121">[App Settings Schema](./appsettings/index.md) Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span>

<span data-ttu-id="14491-122">[Web 設定スキーマ](./web/index.md) IIS などのホスト アプリケーションと ASP.NET の連携を構成する要素も含め、Web 設定スキーマのすべての要素。</span><span class="sxs-lookup"><span data-stu-id="14491-122">[Web Settings Schema](./web/index.md) All elements in the Web settings schema, which includes elements for configuring how ASP.NET works with a host application such as IIS.</span></span> <span data-ttu-id="14491-123">*Aspnet.config* ファイルで使用します。</span><span class="sxs-lookup"><span data-stu-id="14491-123">Used in *Aspnet.config* files.</span></span>

<span data-ttu-id="14491-124">[Windows フォーム構成スキーマ](winforms/index.md) マルチ モニターや高 DPI サポートなどのカスタマイズを含む、Windows フォーム アプリケーションの構成セクションのすべての要素。</span><span class="sxs-lookup"><span data-stu-id="14491-124">[Windows Forms Configuration Schema](winforms/index.md) All elements in the Windows Forms application configuration section, which includes customizations such as multi-monitor and high DPI support.</span></span>

<span data-ttu-id="14491-125">[WCF 構成スキーマ](./wcf/index.md) WCF サービスとクライアント アプリケーションを構成できるすべての要素。</span><span class="sxs-lookup"><span data-stu-id="14491-125">[WCF Configuration Schema](./wcf/index.md) All elements that enable you to configure WCF service and client applications.</span></span>

<span data-ttu-id="14491-126">[WCF ディレクティブ構文](./wcf-directive/index.md) .svc コンパイラによって使用されるページ固有の属性を定義する、`@ServiceHost` ディレクティブについて説明します。</span><span class="sxs-lookup"><span data-stu-id="14491-126">[WCF Directive Syntax](./wcf-directive/index.md) Describes the `@ServiceHost` directive, which defines page-specific attributes used by the .svc compiler.</span></span>

<span data-ttu-id="14491-127">[WIF 構成スキーマ](windows-identity-foundation/index.md) Windows Identity Foundation (WIF) 構成スキーマのすべての要素。</span><span class="sxs-lookup"><span data-stu-id="14491-127">[WIF Configuration Schema](windows-identity-foundation/index.md) All elements of the Windows Identity Foundation (WIF) configuration schema.</span></span>

## <a name="related-sections"></a><span data-ttu-id="14491-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="14491-128">Related sections</span></span>

<span data-ttu-id="14491-129">[リモート処理設定スキーマ](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100)) リモート処理を実装するクライアント アプリケーションとサーバー アプリケーションを構成する要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="14491-129">[Remoting Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100)) Describes the elements that configure client and server applications that implement remoting.</span></span>

<span data-ttu-id="14491-130">[ASP.NET の設定スキーマ](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100)) ASP.NET Web アプリケーションの動作を制御する要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="14491-130">[ASP.NET Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100)) Describes the elements that control the behavior of ASP.NET Web applications.</span></span>

<span data-ttu-id="14491-131">[Web サービス設定スキーマ](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100)) ASP.NET Web サービス、およびそれらのクライアントの動作を制御する要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="14491-131">[Web Services Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100)) Describes the elements that control the behavior of ASP.NET Web services and their clients.</span></span>

<span data-ttu-id="14491-132">[.NET Framework アプリの構成](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/kza1yk3a(v=vs.100)) セキュリティ、アセンブリのバインディング、および .NET Framework のリモート処理を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="14491-132">[Configuring .NET Framework Apps](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/kza1yk3a(v=vs.100)) Describes how to configure security, assembly binding, and remoting in the .NET Framework.</span></span>
