---
title: 'チュートリアル: 暗号化アプリケーションの作成'
description: 暗号化アプリケーションの作成について説明します。 Windows フォームアプリケーションでコンテンツを暗号化および復号化する方法について説明します。
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cryptography [NET Framework], example
- cryptography [NET Framework], cryptographic application example
- cryptography [NET Framework], application example
ms.assetid: abf48c11-1e72-431d-9562-39cf23e1a8ff
ms.openlocfilehash: 72116227fbec2435d428ad2bbdb4cc74e5c3663f
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602181"
---
# <a name="walkthrough-creating-a-cryptographic-application"></a><span data-ttu-id="8fdd8-104">チュートリアル: 暗号化アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="8fdd8-104">Walkthrough: Creating a Cryptographic Application</span></span>
<span data-ttu-id="8fdd8-105">このチュートリアルでは、コンテンツの暗号化および復号化の方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-105">This walkthrough demonstrates how to encrypt and decrypt content.</span></span> <span data-ttu-id="8fdd8-106">コード例は、Windows フォーム アプリケーション向けに設計されています。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-106">The code examples are designed for a Windows Forms application.</span></span> <span data-ttu-id="8fdd8-107">このアプリケーションは、スマート カードを使用するなどの実際のシナリオは示していません。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-107">This application does not demonstrate real world scenarios, such as using smart cards.</span></span> <span data-ttu-id="8fdd8-108">代わりに、暗号化と復号化の基礎を示しています。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-108">Instead, it demonstrates the fundamentals of encryption and decryption.</span></span>  
  
 <span data-ttu-id="8fdd8-109">このチュートリアルでは、次の暗号化のガイドラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-109">This walkthrough uses the following guidelines for encryption:</span></span>  
  
- <span data-ttu-id="8fdd8-110">自動生成される <xref:System.Security.Cryptography.SymmetricAlgorithm.Key%2A> と <xref:System.Security.Cryptography.SymmetricAlgorithm.IV%2A> を使用すると、対称アルゴリズムである <xref:System.Security.Cryptography.RijndaelManaged> クラスでデータの暗号化と復号化を行えます。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-110">Use the <xref:System.Security.Cryptography.RijndaelManaged> class, a symmetric algorithm, to encrypt and decrypt data by using its automatically generated <xref:System.Security.Cryptography.SymmetricAlgorithm.Key%2A> and <xref:System.Security.Cryptography.SymmetricAlgorithm.IV%2A>.</span></span>  
  
- <span data-ttu-id="8fdd8-111">非対称アルゴリズムである <xref:System.Security.Cryptography.RSACryptoServiceProvider> を使用すると、<xref:System.Security.Cryptography.RijndaelManaged> で暗号化されたデータのキーの暗号化と復号化を行えます。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-111">Use the <xref:System.Security.Cryptography.RSACryptoServiceProvider>, an asymmetric algorithm, to encrypt and decrypt the key to the data encrypted by <xref:System.Security.Cryptography.RijndaelManaged>.</span></span> <span data-ttu-id="8fdd8-112">非対称アルゴリズムは、キーなどの少量のデータに最適です。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-112">Asymmetric algorithms are best used for smaller amounts of data, such as a key.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="8fdd8-113">暗号化されたコンテンツを他のユーザーと交換するのではなく、コンピューター上のデータを保護する場合は、<xref:System.Security.Cryptography.ProtectedData> クラスまたは <xref:System.Security.Cryptography.ProtectedMemory> クラスの使用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-113">If you want to protect data on your computer instead of exchanging encrypted content with other people, consider using the <xref:System.Security.Cryptography.ProtectedData> or <xref:System.Security.Cryptography.ProtectedMemory> classes.</span></span>  
  
 <span data-ttu-id="8fdd8-114">次の表は、このトピックの暗号化のタスクをまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-114">The following table summarizes the cryptographic tasks in this topic.</span></span>  
  
|<span data-ttu-id="8fdd8-115">タスク</span><span class="sxs-lookup"><span data-stu-id="8fdd8-115">Task</span></span>|<span data-ttu-id="8fdd8-116">説明</span><span class="sxs-lookup"><span data-stu-id="8fdd8-116">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="8fdd8-117">Windows フォーム アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="8fdd8-117">Creating a Windows Forms application</span></span>|<span data-ttu-id="8fdd8-118">アプリケーションを実行するために必要なコントロールの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-118">Lists the controls that are required to run the application.</span></span>|  
|<span data-ttu-id="8fdd8-119">グローバル オブジェクトの宣言</span><span class="sxs-lookup"><span data-stu-id="8fdd8-119">Declaring global objects</span></span>|<span data-ttu-id="8fdd8-120">文字列のパスの変数、<xref:System.Security.Cryptography.CspParameters>、および <xref:System.Security.Cryptography.RSACryptoServiceProvider> を宣言して、<xref:System.Windows.Forms.Form> クラスのグローバル コンテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-120">Declares string path variables, the <xref:System.Security.Cryptography.CspParameters>, and the <xref:System.Security.Cryptography.RSACryptoServiceProvider> to have global context of the <xref:System.Windows.Forms.Form> class.</span></span>|  
|<span data-ttu-id="8fdd8-121">非対称キーを作成する</span><span class="sxs-lookup"><span data-stu-id="8fdd8-121">Creating an asymmetric key</span></span>|<span data-ttu-id="8fdd8-122">非対称の公開キーと秘密キーの値のペアを作成し、これにキー コンテナー名を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-122">Creates an asymmetric public and private key value pair and assigns it a key container name.</span></span>|  
|<span data-ttu-id="8fdd8-123">ファイルの暗号化</span><span class="sxs-lookup"><span data-stu-id="8fdd8-123">Encrypting a file</span></span>|<span data-ttu-id="8fdd8-124">暗号化するファイルを選択するダイアログ ボックスを表示し、ファイルを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-124">Displays a dialog box to select a file for encryption and encrypts the file.</span></span>|  
|<span data-ttu-id="8fdd8-125">ファイルの復号化</span><span class="sxs-lookup"><span data-stu-id="8fdd8-125">Decrypting a file</span></span>|<span data-ttu-id="8fdd8-126">復号化する暗号化されたファイルを選択するダイアログ ボックスを表示し、ファイルを復号化します。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-126">Displays a dialog box to select an encrypted file for decryption and decrypts the file.</span></span>|  
|<span data-ttu-id="8fdd8-127">秘密キーの取得</span><span class="sxs-lookup"><span data-stu-id="8fdd8-127">Getting a private key</span></span>|<span data-ttu-id="8fdd8-128">キー コンテナー名を使用して、完全なキーのペアを取得します。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-128">Gets the full key pair using the key container name.</span></span>|  
|<span data-ttu-id="8fdd8-129">公開キーのエクスポート</span><span class="sxs-lookup"><span data-stu-id="8fdd8-129">Exporting a public key</span></span>|<span data-ttu-id="8fdd8-130">パブリック パラメーターのみで XML ファイルにキーを保存します。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-130">Saves the key to an XML file with only public parameters.</span></span>|  
|<span data-ttu-id="8fdd8-131">公開キーのインポート</span><span class="sxs-lookup"><span data-stu-id="8fdd8-131">Importing a public key</span></span>|<span data-ttu-id="8fdd8-132">キーを XML ファイルからキー コンテナーに読み込みます。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-132">Loads the key from an XML file into the key container.</span></span>|  
|<span data-ttu-id="8fdd8-133">アプリケーションのテスト</span><span class="sxs-lookup"><span data-stu-id="8fdd8-133">Testing the application</span></span>|<span data-ttu-id="8fdd8-134">このアプリケーションをテストするための手順を一覧に示します。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-134">Lists procedures for testing this application.</span></span>|  
  
## <a name="prerequisites"></a><span data-ttu-id="8fdd8-135">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="8fdd8-135">Prerequisites</span></span>  
 <span data-ttu-id="8fdd8-136">このチュートリアルを実行するには、次のコンポーネントが必要です。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-136">You need the following components to complete this walkthrough:</span></span>  
  
- <span data-ttu-id="8fdd8-137"><xref:System.IO> 名前空間と <xref:System.Security.Cryptography> 名前空間への参照。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-137">References to the <xref:System.IO> and <xref:System.Security.Cryptography> namespaces.</span></span>  
  
## <a name="creating-a-windows-forms-application"></a><span data-ttu-id="8fdd8-138">Windows フォーム アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="8fdd8-138">Creating a Windows Forms Application</span></span>  
 <span data-ttu-id="8fdd8-139">このチュートリアルにあるほとんどのコード例は、ボタン コントロールのイベント ハンドラーとして設計されています。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-139">Most of the code examples in this walkthrough are designed to be event handlers for button controls.</span></span> <span data-ttu-id="8fdd8-140">次の表は、サンプル アプリケーションに必要なコントロールと、コード例に一致する必要な名前を示しています。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-140">The following table lists the controls required for the sample application and their required names to match the code examples.</span></span>  
  
|<span data-ttu-id="8fdd8-141">コントロール</span><span class="sxs-lookup"><span data-stu-id="8fdd8-141">Control</span></span>|<span data-ttu-id="8fdd8-142">名前</span><span class="sxs-lookup"><span data-stu-id="8fdd8-142">Name</span></span>|<span data-ttu-id="8fdd8-143">テキストのプロパティ (必要に応じて)</span><span class="sxs-lookup"><span data-stu-id="8fdd8-143">Text property (as needed)</span></span>|  
|-------------|----------|---------------------------------|  
|<xref:System.Windows.Forms.Button>|`buttonEncryptFile`|<span data-ttu-id="8fdd8-144">ファイルの暗号化</span><span class="sxs-lookup"><span data-stu-id="8fdd8-144">Encrypt File</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonDecryptFile`|<span data-ttu-id="8fdd8-145">ファイルの復号化</span><span class="sxs-lookup"><span data-stu-id="8fdd8-145">Decrypt File</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonCreateAsmKeys`|<span data-ttu-id="8fdd8-146">キーの作成</span><span class="sxs-lookup"><span data-stu-id="8fdd8-146">Create Keys</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonExportPublicKey`|<span data-ttu-id="8fdd8-147">公開キーのエクスポート</span><span class="sxs-lookup"><span data-stu-id="8fdd8-147">Export Public Key</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonImportPublicKey`|<span data-ttu-id="8fdd8-148">公開キーのインポート</span><span class="sxs-lookup"><span data-stu-id="8fdd8-148">Import Public Key</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonGetPrivateKey`|<span data-ttu-id="8fdd8-149">秘密キーの取得</span><span class="sxs-lookup"><span data-stu-id="8fdd8-149">Get Private Key</span></span>|  
|<xref:System.Windows.Forms.Label>|`label1`|<span data-ttu-id="8fdd8-150">キーが設定されていません</span><span class="sxs-lookup"><span data-stu-id="8fdd8-150">Key not set</span></span>|  
|<xref:System.Windows.Forms.OpenFileDialog>|`openFileDialog1`||  
|<xref:System.Windows.Forms.OpenFileDialog>|`openFileDialog2`||  
  
 <span data-ttu-id="8fdd8-151">ボタンのイベント ハンドラーを作成するには、Visual Studio デザイナーでボタンをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-151">Double-click the buttons in the  Visual Studio designer to create their event handlers.</span></span>  
  
## <a name="declaring-global-objects"></a><span data-ttu-id="8fdd8-152">グローバル オブジェクトの宣言</span><span class="sxs-lookup"><span data-stu-id="8fdd8-152">Declaring Global Objects</span></span>  
 <span data-ttu-id="8fdd8-153">次のコードをフォームのコンストラクターに追加します。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-153">Add the following code to the Form's constructor.</span></span> <span data-ttu-id="8fdd8-154">環境とユーザー設定のための文字列変数を編集します。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-154">Edit the string variables for your environment and preferences.</span></span>  
  
 [!code-csharp[CryptoWalkThru#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#1)]
 [!code-vb[CryptoWalkThru#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#1)]  
  
## <a name="creating-an-asymmetric-key"></a><span data-ttu-id="8fdd8-155">非対称キーの作成</span><span class="sxs-lookup"><span data-stu-id="8fdd8-155">Creating an Asymmetric Key</span></span>  
 <span data-ttu-id="8fdd8-156">この作業では、<xref:System.Security.Cryptography.RijndaelManaged> キーの暗号化と復号化を行う非対称キーを作成します。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-156">This task creates an asymmetric key that encrypts and decrypts the <xref:System.Security.Cryptography.RijndaelManaged> key.</span></span> <span data-ttu-id="8fdd8-157">このキーは、コンテンツの暗号化に使用されたもので、ラベル コントロールにキー コンテナー名を表示します。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-157">This key was used to encrypt the content and it displays the key container name on the label control.</span></span>  
  
 <span data-ttu-id="8fdd8-158">次のコードを [`Create Keys`] ボタン (`buttonCreateAsmKeys_Click`) の `Click` イベント ハンドラーとして追加します。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-158">Add the following code as the `Click` event handler for the `Create Keys` button (`buttonCreateAsmKeys_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#2)]
 [!code-vb[CryptoWalkThru#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#2)]  
  
## <a name="encrypting-a-file"></a><span data-ttu-id="8fdd8-159">ファイルの暗号化</span><span class="sxs-lookup"><span data-stu-id="8fdd8-159">Encrypting a File</span></span>  
 <span data-ttu-id="8fdd8-160">このタスクには、ボタン () のイベントハンドラーメソッド `Encrypt File` とメソッドの2つのメソッドが含ま `buttonEncryptFile_Click` れます。 `EncryptFile`</span><span class="sxs-lookup"><span data-stu-id="8fdd8-160">This task involves two methods: the event handler method for the `Encrypt File` button (`buttonEncryptFile_Click`) and the `EncryptFile` method.</span></span> <span data-ttu-id="8fdd8-161">最初のメソッドは、ファイルを選択するためのダイアログ ボックスを表示し、暗号化を実行する 2 番目のメソッドにファイル名を渡します。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-161">The first method displays a dialog box for selecting a file and passes the file name to the second method, which performs the encryption.</span></span>  
  
 <span data-ttu-id="8fdd8-162">暗号化されたコンテンツ、キー、および IV は、すべて 1 つの <xref:System.IO.FileStream> に保存されます。これを暗号化パッケージといいます。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-162">The encrypted content, key, and IV are all saved to one <xref:System.IO.FileStream>, which is referred to as the encryption package.</span></span>  
  
 <span data-ttu-id="8fdd8-163">`EncryptFile` メソッドは以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-163">The `EncryptFile` method does the following:</span></span>  
  
1. <span data-ttu-id="8fdd8-164">コンテンツを暗号化する <xref:System.Security.Cryptography.RijndaelManaged> 対称アルゴリズムを作成します。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-164">Creates a <xref:System.Security.Cryptography.RijndaelManaged> symmetric algorithm to encrypt the content.</span></span>  
  
2. <span data-ttu-id="8fdd8-165"><xref:System.Security.Cryptography.RijndaelManaged> キーを暗号化する <xref:System.Security.Cryptography.RSACryptoServiceProvider> オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-165">Creates an <xref:System.Security.Cryptography.RSACryptoServiceProvider> object to encrypt the <xref:System.Security.Cryptography.RijndaelManaged> key.</span></span>  
  
3. <span data-ttu-id="8fdd8-166">ソース ファイルの <xref:System.IO.FileStream> の読み取りと暗号化を行う <xref:System.Security.Cryptography.CryptoStream> オブジェクト (バイトのブロック) を使用して、暗号化ファイルの対象の <xref:System.IO.FileStream> オブジェクトにします。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-166">Uses a <xref:System.Security.Cryptography.CryptoStream> object to read and encrypt the <xref:System.IO.FileStream> of the source file, in blocks of bytes, into a destination <xref:System.IO.FileStream> object for the encrypted file.</span></span>  
  
4. <span data-ttu-id="8fdd8-167">暗号化されたキーと IV の長さを決定し、長さの値のバイト配列を作成します。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-167">Determines the lengths of the encrypted key and IV, and creates byte arrays of their length values.</span></span>  
  
5. <span data-ttu-id="8fdd8-168">暗号化されたパッケージにキー、IV、および長さの値を書き込みます。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-168">Writes the Key, IV, and their length values to the encrypted package.</span></span>  
  
 <span data-ttu-id="8fdd8-169">暗号化パッケージでは、次の形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-169">The encryption package uses the following format:</span></span>  
  
- <span data-ttu-id="8fdd8-170">キーの長さ: 0 - 3 バイト</span><span class="sxs-lookup"><span data-stu-id="8fdd8-170">Key length, bytes 0 - 3</span></span>  
  
- <span data-ttu-id="8fdd8-171">IV の長さ: 4 - 7 バイト</span><span class="sxs-lookup"><span data-stu-id="8fdd8-171">IV length, bytes 4 - 7</span></span>  
  
- <span data-ttu-id="8fdd8-172">暗号化されたキー</span><span class="sxs-lookup"><span data-stu-id="8fdd8-172">Encrypted key</span></span>  
  
- <span data-ttu-id="8fdd8-173">IV</span><span class="sxs-lookup"><span data-stu-id="8fdd8-173">IV</span></span>  
  
- <span data-ttu-id="8fdd8-174">暗号化テキスト</span><span class="sxs-lookup"><span data-stu-id="8fdd8-174">Cipher text</span></span>  
  
 <span data-ttu-id="8fdd8-175">キーと IV の長さを使用すると、暗号化パッケージのすべての部分の開始点と長さを決定することができます。これを使用してファイルを復号化します。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-175">You can use the lengths of the key and IV to determine the starting points and lengths of all parts of the encryption package, which can then be used to decrypt the file.</span></span>  
  
 <span data-ttu-id="8fdd8-176">次のコードを [`Encrypt File`] ボタン (`buttonEncryptFile_Click`) の `Click` イベント ハンドラーとして追加します。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-176">Add the following code as the `Click` event handler for the `Encrypt File` button (`buttonEncryptFile_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#3)]
 [!code-vb[CryptoWalkThru#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#3)]  
  
 <span data-ttu-id="8fdd8-177">フォームに次の `EncryptFile` メソッドを追加します。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-177">Add the following `EncryptFile` method to the form.</span></span>  
  
 [!code-csharp[CryptoWalkThru#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#5)]
 [!code-vb[CryptoWalkThru#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#5)]  
  
## <a name="decrypting-a-file"></a><span data-ttu-id="8fdd8-178">ファイルの復号化</span><span class="sxs-lookup"><span data-stu-id="8fdd8-178">Decrypting a File</span></span>  
 <span data-ttu-id="8fdd8-179">このタスクには、[`Decrypt File`] ボタン (`buttonDecryptFile_Click`) のイベント ハンドラー メソッドと `DecryptFile` メソッドという 2 つのメソッドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-179">This task involves two methods, the event handler method for the `Decrypt File` button (`buttonDecryptFile_Click`), and the `DecryptFile` method.</span></span> <span data-ttu-id="8fdd8-180">最初のメソッドは、ファイルを選択するためのダイアログ ボックスを表示し、復号化を実行する 2 番目のメソッドにファイル名を渡します。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-180">The first method displays a dialog box for selecting a file and passes its file name to the second method, which performs the decryption.</span></span>  
  
 <span data-ttu-id="8fdd8-181">`Decrypt` メソッドは以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-181">The `Decrypt` method does the following:</span></span>  
  
1. <span data-ttu-id="8fdd8-182">コンテンツを復号化する <xref:System.Security.Cryptography.RijndaelManaged> の対称アルゴリズムを作成します。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-182">Creates a <xref:System.Security.Cryptography.RijndaelManaged> symmetric algorithm to decrypt the content.</span></span>  
  
2. <span data-ttu-id="8fdd8-183">暗号化されたキーと IV の長さを取得するには、暗号化パッケージの <xref:System.IO.FileStream> の最初の 8 バイトを読み取ってバイト配列にします。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-183">Reads the first eight bytes of the <xref:System.IO.FileStream> of the encrypted package into byte arrays to obtain the lengths of the encrypted key and the IV.</span></span>  
  
3. <span data-ttu-id="8fdd8-184">キーと IV を暗号化パッケージから抽出してバイト配列にします。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-184">Extracts the key and IV from the encryption package into byte arrays.</span></span>  
  
4. <span data-ttu-id="8fdd8-185"><xref:System.Security.Cryptography.RijndaelManaged> キーを復号化する <xref:System.Security.Cryptography.RSACryptoServiceProvider> オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-185">Creates an <xref:System.Security.Cryptography.RSACryptoServiceProvider> object to decrypt the <xref:System.Security.Cryptography.RijndaelManaged> key.</span></span>  
  
5. <span data-ttu-id="8fdd8-186"><xref:System.Security.Cryptography.CryptoStream> オブジェクトを使用して、<xref:System.IO.FileStream> の暗号化パッケージの暗号テキスト セクションをバイトのブロックで読み取って復号化し、復号化されたファイルの <xref:System.IO.FileStream> オブジェクトにします。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-186">Uses a <xref:System.Security.Cryptography.CryptoStream> object to read and decrypt the cipher text section of the <xref:System.IO.FileStream> encryption package, in blocks of bytes, into the <xref:System.IO.FileStream> object for the decrypted file.</span></span> <span data-ttu-id="8fdd8-187">これが終了すると、復号化は完了です。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-187">When this is finished, the decryption is completed.</span></span>  
  
 <span data-ttu-id="8fdd8-188">次のコードを、[`Decrypt File`] ボタンの `Click` イベント ハンドラーとして追加します。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-188">Add the following code as the `Click` event handler for the `Decrypt File` button.</span></span>  
  
 [!code-csharp[CryptoWalkThru#4](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#4)]
 [!code-vb[CryptoWalkThru#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#4)]  
  
 <span data-ttu-id="8fdd8-189">フォームに次の `DecryptFile` メソッドを追加します。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-189">Add the following `DecryptFile` method to the form.</span></span>  
  
 [!code-csharp[CryptoWalkThru#6](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#6)]
 [!code-vb[CryptoWalkThru#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#6)]  
  
## <a name="exporting-a-public-key"></a><span data-ttu-id="8fdd8-190">公開キーのエクスポート</span><span class="sxs-lookup"><span data-stu-id="8fdd8-190">Exporting a Public Key</span></span>  
 <span data-ttu-id="8fdd8-191">この作業では、[`Create Keys`] ボタンによって作成されたキーをファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-191">This task saves the key created by the `Create Keys` button to a file.</span></span> <span data-ttu-id="8fdd8-192">パブリック パラメーターのみがエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-192">It exports only the public parameters.</span></span>  
  
 <span data-ttu-id="8fdd8-193">このタスクでは、アリスがボブに公開キーを与えるシナリオをシミュレーションします。そうすることで、ボブはアリスのファイルを暗号化できるようになります。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-193">This task simulates the scenario of Alice giving Bob her public key so that he can encrypt files for her.</span></span> <span data-ttu-id="8fdd8-194">ボブとその公開キーを持つ他のユーザーはファイルを復号化できなくなります。彼らはプライベート パラメーターを持つ完全なキーのペアを持っていないためです。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-194">He and others who have that public key will not be able to decrypt them because they do not have the full key pair with private parameters.</span></span>  
  
 <span data-ttu-id="8fdd8-195">次のコードを [`Export Public Key`] ボタン (`buttonExportPublicKey_Click`) の `Click` イベント ハンドラーとして追加します。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-195">Add the following code as the `Click` event handler for the `Export Public Key` button (`buttonExportPublicKey_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#8](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#8)]
 [!code-vb[CryptoWalkThru#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#8)]  
  
## <a name="importing-a-public-key"></a><span data-ttu-id="8fdd8-196">公開キーのインポート</span><span class="sxs-lookup"><span data-stu-id="8fdd8-196">Importing a Public Key</span></span>  
 <span data-ttu-id="8fdd8-197">このタスクでは、[`Export Public Key`] ボタンによって作成されたパブリック パラメーターのみを持つキーを読み込み、キー コンテナー名として設定します。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-197">This task loads the key with only public parameters, as created by the `Export Public Key` button, and sets it as the key container name.</span></span>  
  
 <span data-ttu-id="8fdd8-198">この作業では、ボブがアリスのファイルを暗号化できるように、ボブがパブリック パラメーターのみを持つアリスのキーを読み込むシナリオをシミュレーションします。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-198">This task simulates the scenario of Bob loading Alice's key with only public parameters so he can encrypt files for her.</span></span>  
  
 <span data-ttu-id="8fdd8-199">次のコードを [`Import Public Key`] ボタン (`buttonImportPublicKey_Click`) の `Click` イベント ハンドラーとして追加します。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-199">Add the following code as the `Click` event handler for the `Import Public Key` button (`buttonImportPublicKey_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#9](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#9)]
 [!code-vb[CryptoWalkThru#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#9)]  
  
## <a name="getting-a-private-key"></a><span data-ttu-id="8fdd8-200">秘密キーの取得</span><span class="sxs-lookup"><span data-stu-id="8fdd8-200">Getting a Private Key</span></span>  
 <span data-ttu-id="8fdd8-201">この作業では、[`Create Keys`] ボタンを使用して作成されたキーの名前にキー コンテナー名を設定します。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-201">This task sets the key container name to the name of the key created by using the `Create Keys` button.</span></span> <span data-ttu-id="8fdd8-202">キー コンテナーには、プライベート パラメーターを持つ完全なキーのペアが格納されます。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-202">The key container will contain the full key pair with private parameters.</span></span>  
  
 <span data-ttu-id="8fdd8-203">この作業では、アリスが自分の秘密キーを使用してボブが暗号化したファイルを復号化するシナリオをシミュレーションします。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-203">This task simulates the scenario of Alice using her private key to decrypt files encrypted by Bob.</span></span>  
  
 <span data-ttu-id="8fdd8-204">次のコードを [`Get Private Key`] ボタン (`buttonGetPrivateKey_Click`) の `Click` イベント ハンドラーとして追加します。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-204">Add the following code as the `Click` event handler for the `Get Private Key` button (`buttonGetPrivateKey_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#7](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#7)]
 [!code-vb[CryptoWalkThru#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#7)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="8fdd8-205">アプリケーションのテスト</span><span class="sxs-lookup"><span data-stu-id="8fdd8-205">Testing the Application</span></span>  
 <span data-ttu-id="8fdd8-206">アプリケーションをビルドしたら、次のテスト シナリオを実行します。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-206">After you have built the application, perform the following testing scenarios.</span></span>  
  
#### <a name="to-create-keys-encrypt-and-decrypt"></a><span data-ttu-id="8fdd8-207">キーの作成、暗号化、および復号化を行うには</span><span class="sxs-lookup"><span data-stu-id="8fdd8-207">To create keys, encrypt, and decrypt</span></span>  
  
1. <span data-ttu-id="8fdd8-208">`Create Keys` ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-208">Click the `Create Keys` button.</span></span> <span data-ttu-id="8fdd8-209">ラベルはキー名を表示し、完全なキーのペアであることを示します。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-209">The label displays the key name and shows that it is a full key pair.</span></span>  
  
2. <span data-ttu-id="8fdd8-210">`Export Public Key` ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-210">Click the `Export Public Key` button.</span></span> <span data-ttu-id="8fdd8-211">公開キーのパラメーターのエクスポートにより現在のキーは変更されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-211">Note that exporting the public key parameters does not change the current key.</span></span>  
  
3. <span data-ttu-id="8fdd8-212">[`Encrypt File`] ボタンをクリックして、ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-212">Click the `Encrypt File` button and select a file.</span></span>  
  
4. <span data-ttu-id="8fdd8-213">[`Decrypt File`] ボタンをクリックし、暗号化したファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-213">Click the `Decrypt File` button and select the file just encrypted.</span></span>  
  
5. <span data-ttu-id="8fdd8-214">復号化したファイルを調べます。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-214">Examine the file just decrypted.</span></span>  
  
6. <span data-ttu-id="8fdd8-215">次のシナリオで保持されたキー コンテナーを取得するテストを実行するには、アプリケーションを閉じて再起動します。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-215">Close the application and restart it to test retrieving persisted key containers in the next scenario.</span></span>  
  
#### <a name="to-encrypt-using-the-public-key"></a><span data-ttu-id="8fdd8-216">公開キーを使用して暗号化するには</span><span class="sxs-lookup"><span data-stu-id="8fdd8-216">To encrypt using the public key</span></span>  
  
1. <span data-ttu-id="8fdd8-217">`Import Public Key` ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-217">Click the `Import Public Key` button.</span></span> <span data-ttu-id="8fdd8-218">ラベルはキー名を表示し、公開キーのみであることを示します。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-218">The label displays the key name and shows that it is public only.</span></span>  
  
2. <span data-ttu-id="8fdd8-219">[`Encrypt File`] ボタンをクリックして、ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-219">Click the `Encrypt File` button and select a file.</span></span>  
  
3. <span data-ttu-id="8fdd8-220">[`Decrypt File`] ボタンをクリックし、暗号化したファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-220">Click the `Decrypt File` button and select the file just encrypted.</span></span> <span data-ttu-id="8fdd8-221">復号化するには秘密キーが必要であるため、これは失敗します。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-221">This will fail because you must have the private key to decrypt.</span></span>  
  
 <span data-ttu-id="8fdd8-222">このシナリオでは、公開キーのみによる別のユーザーのファイルの暗号化をデモンストレーションします。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-222">This scenario demonstrates having only the public key to encrypt a file for another person.</span></span> <span data-ttu-id="8fdd8-223">通常、そのユーザーは公開キーのみを与え、秘密キーは復号化のため与えないでおきます。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-223">Typically that person would give you only the public key and withhold the private key for decryption.</span></span>  
  
#### <a name="to-decrypt-using-the-private-key"></a><span data-ttu-id="8fdd8-224">秘密キーを使用して復号化するには</span><span class="sxs-lookup"><span data-stu-id="8fdd8-224">To decrypt using the private key</span></span>  
  
1. <span data-ttu-id="8fdd8-225">`Get Private Key` ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-225">Click the `Get Private Key` button.</span></span> <span data-ttu-id="8fdd8-226">ラベルはキー名を表示し、完全なキーのペアであるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-226">The label displays the key name and shows whether it is the full key pair.</span></span>  
  
2. <span data-ttu-id="8fdd8-227">[`Decrypt File`] ボタンをクリックし、暗号化したファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-227">Click the `Decrypt File` button and select the file just encrypted.</span></span> <span data-ttu-id="8fdd8-228">復号化するための完全なキーのペアがあるため、これは成功します。</span><span class="sxs-lookup"><span data-stu-id="8fdd8-228">This will be successful because you have the full key pair to decrypt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fdd8-229">関連項目</span><span class="sxs-lookup"><span data-stu-id="8fdd8-229">See also</span></span>

- [<span data-ttu-id="8fdd8-230">暗号化サービス</span><span class="sxs-lookup"><span data-stu-id="8fdd8-230">Cryptographic Services</span></span>](cryptographic-services.md)
