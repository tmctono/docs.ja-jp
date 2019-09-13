---
title: 'チュートリアル: 暗号化アプリケーションの作成'
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ee6dafa8578c59d23908bf0e184091bb4ceaeb45
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/11/2019
ms.locfileid: "70895287"
---
# <a name="walkthrough-creating-a-cryptographic-application"></a><span data-ttu-id="ad3de-102">チュートリアル: 暗号化アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="ad3de-102">Walkthrough: Creating a Cryptographic Application</span></span>
<span data-ttu-id="ad3de-103">このチュートリアルでは、コンテンツの暗号化および復号化の方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ad3de-103">This walkthrough demonstrates how to encrypt and decrypt content.</span></span> <span data-ttu-id="ad3de-104">コード例は、Windows フォーム アプリケーション向けに設計されています。</span><span class="sxs-lookup"><span data-stu-id="ad3de-104">The code examples are designed for a Windows Forms application.</span></span> <span data-ttu-id="ad3de-105">このアプリケーションは、スマート カードを使用するなどの実際のシナリオは示していません。</span><span class="sxs-lookup"><span data-stu-id="ad3de-105">This application does not demonstrate real world scenarios, such as using smart cards.</span></span> <span data-ttu-id="ad3de-106">代わりに、暗号化と復号化の基礎を示しています。</span><span class="sxs-lookup"><span data-stu-id="ad3de-106">Instead, it demonstrates the fundamentals of encryption and decryption.</span></span>  
  
 <span data-ttu-id="ad3de-107">このチュートリアルでは、次の暗号化のガイドラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="ad3de-107">This walkthrough uses the following guidelines for encryption:</span></span>  
  
- <span data-ttu-id="ad3de-108">自動生成される <xref:System.Security.Cryptography.SymmetricAlgorithm.Key%2A> と <xref:System.Security.Cryptography.SymmetricAlgorithm.IV%2A> を使用すると、対称アルゴリズムである <xref:System.Security.Cryptography.RijndaelManaged> クラスでデータの暗号化と復号化を行えます。</span><span class="sxs-lookup"><span data-stu-id="ad3de-108">Use the <xref:System.Security.Cryptography.RijndaelManaged> class, a symmetric algorithm, to encrypt and decrypt data by using its automatically generated <xref:System.Security.Cryptography.SymmetricAlgorithm.Key%2A> and <xref:System.Security.Cryptography.SymmetricAlgorithm.IV%2A>.</span></span>  
  
- <span data-ttu-id="ad3de-109">非対称アルゴリズムである <xref:System.Security.Cryptography.RSACryptoServiceProvider> を使用すると、<xref:System.Security.Cryptography.RijndaelManaged> で暗号化されたデータのキーの暗号化と復号化を行えます。</span><span class="sxs-lookup"><span data-stu-id="ad3de-109">Use the <xref:System.Security.Cryptography.RSACryptoServiceProvider>, an asymmetric algorithm, to encrypt and decrypt the key to the data encrypted by <xref:System.Security.Cryptography.RijndaelManaged>.</span></span> <span data-ttu-id="ad3de-110">非対称アルゴリズムは、キーなどの少量のデータに最適です。</span><span class="sxs-lookup"><span data-stu-id="ad3de-110">Asymmetric algorithms are best used for smaller amounts of data, such as a key.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="ad3de-111">暗号化されたコンテンツを他のユーザーと交換するのではなく、コンピューター上のデータを保護する場合は、<xref:System.Security.Cryptography.ProtectedData> クラスまたは <xref:System.Security.Cryptography.ProtectedMemory> クラスの使用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="ad3de-111">If you want to protect data on your computer instead of exchanging encrypted content with other people, consider using the <xref:System.Security.Cryptography.ProtectedData> or <xref:System.Security.Cryptography.ProtectedMemory> classes.</span></span>  
  
 <span data-ttu-id="ad3de-112">次の表は、このトピックの暗号化のタスクをまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="ad3de-112">The following table summarizes the cryptographic tasks in this topic.</span></span>  
  
|<span data-ttu-id="ad3de-113">タスク</span><span class="sxs-lookup"><span data-stu-id="ad3de-113">Task</span></span>|<span data-ttu-id="ad3de-114">説明</span><span class="sxs-lookup"><span data-stu-id="ad3de-114">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="ad3de-115">Windows フォーム アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="ad3de-115">Creating a Windows Forms application</span></span>|<span data-ttu-id="ad3de-116">アプリケーションを実行するために必要なコントロールの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="ad3de-116">Lists the controls that are required to run the application.</span></span>|  
|<span data-ttu-id="ad3de-117">グローバル オブジェクトの宣言</span><span class="sxs-lookup"><span data-stu-id="ad3de-117">Declaring global objects</span></span>|<span data-ttu-id="ad3de-118">文字列のパスの変数、<xref:System.Security.Cryptography.CspParameters>、および <xref:System.Security.Cryptography.RSACryptoServiceProvider> を宣言して、<xref:System.Windows.Forms.Form> クラスのグローバル コンテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="ad3de-118">Declares string path variables, the <xref:System.Security.Cryptography.CspParameters>, and the <xref:System.Security.Cryptography.RSACryptoServiceProvider> to have global context of the <xref:System.Windows.Forms.Form> class.</span></span>|  
|<span data-ttu-id="ad3de-119">非対称キーの作成</span><span class="sxs-lookup"><span data-stu-id="ad3de-119">Creating an asymmetric key</span></span>|<span data-ttu-id="ad3de-120">非対称の公開キーと秘密キーの値のペアを作成し、これにキー コンテナー名を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ad3de-120">Creates an asymmetric public and private key value pair and assigns it a key container name.</span></span>|  
|<span data-ttu-id="ad3de-121">ファイルの暗号化</span><span class="sxs-lookup"><span data-stu-id="ad3de-121">Encrypting a file</span></span>|<span data-ttu-id="ad3de-122">暗号化するファイルを選択するダイアログ ボックスを表示し、ファイルを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="ad3de-122">Displays a dialog box to select a file for encryption and encrypts the file.</span></span>|  
|<span data-ttu-id="ad3de-123">ファイルの復号化</span><span class="sxs-lookup"><span data-stu-id="ad3de-123">Decrypting a file</span></span>|<span data-ttu-id="ad3de-124">復号化する暗号化されたファイルを選択するダイアログ ボックスを表示し、ファイルを復号化します。</span><span class="sxs-lookup"><span data-stu-id="ad3de-124">Displays a dialog box to select an encrypted file for decryption and decrypts the file.</span></span>|  
|<span data-ttu-id="ad3de-125">秘密キーの取得</span><span class="sxs-lookup"><span data-stu-id="ad3de-125">Getting a private key</span></span>|<span data-ttu-id="ad3de-126">キー コンテナー名を使用して、完全なキーのペアを取得します。</span><span class="sxs-lookup"><span data-stu-id="ad3de-126">Gets the full key pair using the key container name.</span></span>|  
|<span data-ttu-id="ad3de-127">公開キーのエクスポート</span><span class="sxs-lookup"><span data-stu-id="ad3de-127">Exporting a public key</span></span>|<span data-ttu-id="ad3de-128">パブリック パラメーターのみで XML ファイルにキーを保存します。</span><span class="sxs-lookup"><span data-stu-id="ad3de-128">Saves the key to an XML file with only public parameters.</span></span>|  
|<span data-ttu-id="ad3de-129">公開キーのインポート</span><span class="sxs-lookup"><span data-stu-id="ad3de-129">Importing a public key</span></span>|<span data-ttu-id="ad3de-130">キーを XML ファイルからキー コンテナーに読み込みます。</span><span class="sxs-lookup"><span data-stu-id="ad3de-130">Loads the key from an XML file into the key container.</span></span>|  
|<span data-ttu-id="ad3de-131">アプリケーションのテスト</span><span class="sxs-lookup"><span data-stu-id="ad3de-131">Testing the application</span></span>|<span data-ttu-id="ad3de-132">このアプリケーションをテストするための手順を一覧に示します。</span><span class="sxs-lookup"><span data-stu-id="ad3de-132">Lists procedures for testing this application.</span></span>|  
  
## <a name="prerequisites"></a><span data-ttu-id="ad3de-133">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ad3de-133">Prerequisites</span></span>  
 <span data-ttu-id="ad3de-134">このチュートリアルを実行するには、次のコンポーネントが必要です。</span><span class="sxs-lookup"><span data-stu-id="ad3de-134">You need the following components to complete this walkthrough:</span></span>  
  
- <span data-ttu-id="ad3de-135"><xref:System.IO> 名前空間と <xref:System.Security.Cryptography> 名前空間への参照。</span><span class="sxs-lookup"><span data-stu-id="ad3de-135">References to the <xref:System.IO> and <xref:System.Security.Cryptography> namespaces.</span></span>  
  
## <a name="creating-a-windows-forms-application"></a><span data-ttu-id="ad3de-136">Windows フォーム アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="ad3de-136">Creating a Windows Forms Application</span></span>  
 <span data-ttu-id="ad3de-137">このチュートリアルにあるほとんどのコード例は、ボタン コントロールのイベント ハンドラーとして設計されています。</span><span class="sxs-lookup"><span data-stu-id="ad3de-137">Most of the code examples in this walkthrough are designed to be event handlers for button controls.</span></span> <span data-ttu-id="ad3de-138">次の表は、サンプル アプリケーションに必要なコントロールと、コード例に一致する必要な名前を示しています。</span><span class="sxs-lookup"><span data-stu-id="ad3de-138">The following table lists the controls required for the sample application and their required names to match the code examples.</span></span>  
  
|<span data-ttu-id="ad3de-139">コントロール</span><span class="sxs-lookup"><span data-stu-id="ad3de-139">Control</span></span>|<span data-ttu-id="ad3de-140">Name</span><span class="sxs-lookup"><span data-stu-id="ad3de-140">Name</span></span>|<span data-ttu-id="ad3de-141">テキストのプロパティ (必要に応じて)</span><span class="sxs-lookup"><span data-stu-id="ad3de-141">Text property (as needed)</span></span>|  
|-------------|----------|---------------------------------|  
|<xref:System.Windows.Forms.Button>|`buttonEncryptFile`|<span data-ttu-id="ad3de-142">ファイルの暗号化</span><span class="sxs-lookup"><span data-stu-id="ad3de-142">Encrypt File</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonDecryptFile`|<span data-ttu-id="ad3de-143">ファイルの復号化</span><span class="sxs-lookup"><span data-stu-id="ad3de-143">Decrypt File</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonCreateAsmKeys`|<span data-ttu-id="ad3de-144">キーの作成</span><span class="sxs-lookup"><span data-stu-id="ad3de-144">Create Keys</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonExportPublicKey`|<span data-ttu-id="ad3de-145">公開キーのエクスポート</span><span class="sxs-lookup"><span data-stu-id="ad3de-145">Export Public Key</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonImportPublicKey`|<span data-ttu-id="ad3de-146">公開キーのインポート</span><span class="sxs-lookup"><span data-stu-id="ad3de-146">Import Public Key</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonGetPrivateKey`|<span data-ttu-id="ad3de-147">秘密キーの取得</span><span class="sxs-lookup"><span data-stu-id="ad3de-147">Get Private Key</span></span>|  
|<xref:System.Windows.Forms.Label>|`label1`|<span data-ttu-id="ad3de-148">キーが設定されていません</span><span class="sxs-lookup"><span data-stu-id="ad3de-148">Key not set</span></span>|  
|<xref:System.Windows.Forms.OpenFileDialog>|`openFileDialog1`||  
|<xref:System.Windows.Forms.OpenFileDialog>|`openFileDialog2`||  
  
 <span data-ttu-id="ad3de-149">ボタンのイベント ハンドラーを作成するには、Visual Studio デザイナーでボタンをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad3de-149">Double-click the buttons in the  Visual Studio designer to create their event handlers.</span></span>  
  
## <a name="declaring-global-objects"></a><span data-ttu-id="ad3de-150">グローバル オブジェクトの宣言</span><span class="sxs-lookup"><span data-stu-id="ad3de-150">Declaring Global Objects</span></span>  
 <span data-ttu-id="ad3de-151">次のコードをフォームのコンストラクターに追加します。</span><span class="sxs-lookup"><span data-stu-id="ad3de-151">Add the following code to the Form's constructor.</span></span> <span data-ttu-id="ad3de-152">環境とユーザー設定のための文字列変数を編集します。</span><span class="sxs-lookup"><span data-stu-id="ad3de-152">Edit the string variables for your environment and preferences.</span></span>  
  
 [!code-csharp[CryptoWalkThru#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#1)]
 [!code-vb[CryptoWalkThru#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#1)]  
  
## <a name="creating-an-asymmetric-key"></a><span data-ttu-id="ad3de-153">非対称キーの作成</span><span class="sxs-lookup"><span data-stu-id="ad3de-153">Creating an Asymmetric Key</span></span>  
 <span data-ttu-id="ad3de-154">この作業では、<xref:System.Security.Cryptography.RijndaelManaged> キーの暗号化と復号化を行う非対称キーを作成します。</span><span class="sxs-lookup"><span data-stu-id="ad3de-154">This task creates an asymmetric key that encrypts and decrypts the <xref:System.Security.Cryptography.RijndaelManaged> key.</span></span> <span data-ttu-id="ad3de-155">このキーは、コンテンツの暗号化に使用されたもので、ラベル コントロールにキー コンテナー名を表示します。</span><span class="sxs-lookup"><span data-stu-id="ad3de-155">This key was used to encrypt the content and it displays the key container name on the label control.</span></span>  
  
 <span data-ttu-id="ad3de-156">次のコードを [`Create Keys`] ボタン (`buttonCreateAsmKeys_Click`) の `Click` イベント ハンドラーとして追加します。</span><span class="sxs-lookup"><span data-stu-id="ad3de-156">Add the following code as the `Click` event handler for the `Create Keys` button (`buttonCreateAsmKeys_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#2)]
 [!code-vb[CryptoWalkThru#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#2)]  
  
## <a name="encrypting-a-file"></a><span data-ttu-id="ad3de-157">ファイルの暗号化</span><span class="sxs-lookup"><span data-stu-id="ad3de-157">Encrypting a File</span></span>  
 <span data-ttu-id="ad3de-158">このタスクには、 `Encrypt File`ボタン (`buttonEncryptFile_Click`) のイベントハンドラーメソッドと`EncryptFile`メソッドの2つのメソッドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ad3de-158">This task involves two methods: the event handler method for the `Encrypt File` button (`buttonEncryptFile_Click`) and the `EncryptFile` method.</span></span> <span data-ttu-id="ad3de-159">最初のメソッドは、ファイルを選択するためのダイアログ ボックスを表示し、暗号化を実行する 2 番目のメソッドにファイル名を渡します。</span><span class="sxs-lookup"><span data-stu-id="ad3de-159">The first method displays a dialog box for selecting a file and passes the file name to the second method, which performs the encryption.</span></span>  
  
 <span data-ttu-id="ad3de-160">暗号化されたコンテンツ、キー、および IV は、すべて 1 つの <xref:System.IO.FileStream> に保存されます。これを暗号化パッケージといいます。</span><span class="sxs-lookup"><span data-stu-id="ad3de-160">The encrypted content, key, and IV are all saved to one <xref:System.IO.FileStream>, which is referred to as the encryption package.</span></span>  
  
 <span data-ttu-id="ad3de-161">`EncryptFile` メソッドは以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="ad3de-161">The `EncryptFile` method does the following:</span></span>  
  
1. <span data-ttu-id="ad3de-162">コンテンツを暗号化する <xref:System.Security.Cryptography.RijndaelManaged> 対称アルゴリズムを作成します。</span><span class="sxs-lookup"><span data-stu-id="ad3de-162">Creates a <xref:System.Security.Cryptography.RijndaelManaged> symmetric algorithm to encrypt the content.</span></span>  
  
2. <span data-ttu-id="ad3de-163"><xref:System.Security.Cryptography.RijndaelManaged> キーを暗号化する <xref:System.Security.Cryptography.RSACryptoServiceProvider> オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="ad3de-163">Creates an <xref:System.Security.Cryptography.RSACryptoServiceProvider> object to encrypt the <xref:System.Security.Cryptography.RijndaelManaged> key.</span></span>  
  
3. <span data-ttu-id="ad3de-164">ソース ファイルの <xref:System.IO.FileStream> の読み取りと暗号化を行う <xref:System.Security.Cryptography.CryptoStream> オブジェクト (バイトのブロック) を使用して、暗号化ファイルの対象の <xref:System.IO.FileStream> オブジェクトにします。</span><span class="sxs-lookup"><span data-stu-id="ad3de-164">Uses a <xref:System.Security.Cryptography.CryptoStream> object to read and encrypt the <xref:System.IO.FileStream> of the source file, in blocks of bytes, into a destination <xref:System.IO.FileStream> object for the encrypted file.</span></span>  
  
4. <span data-ttu-id="ad3de-165">暗号化されたキーと IV の長さを決定し、長さの値のバイト配列を作成します。</span><span class="sxs-lookup"><span data-stu-id="ad3de-165">Determines the lengths of the encrypted key and IV, and creates byte arrays of their length values.</span></span>  
  
5. <span data-ttu-id="ad3de-166">暗号化されたパッケージにキー、IV、および長さの値を書き込みます。</span><span class="sxs-lookup"><span data-stu-id="ad3de-166">Writes the Key, IV, and their length values to the encrypted package.</span></span>  
  
 <span data-ttu-id="ad3de-167">暗号化パッケージでは、次の形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="ad3de-167">The encryption package uses the following format:</span></span>  
  
- <span data-ttu-id="ad3de-168">キーの長さ: 0 - 3 バイト</span><span class="sxs-lookup"><span data-stu-id="ad3de-168">Key length, bytes 0 - 3</span></span>  
  
- <span data-ttu-id="ad3de-169">IV の長さ: 4 - 7 バイト</span><span class="sxs-lookup"><span data-stu-id="ad3de-169">IV length, bytes 4 - 7</span></span>  
  
- <span data-ttu-id="ad3de-170">暗号化されたキー</span><span class="sxs-lookup"><span data-stu-id="ad3de-170">Encrypted key</span></span>  
  
- <span data-ttu-id="ad3de-171">IV</span><span class="sxs-lookup"><span data-stu-id="ad3de-171">IV</span></span>  
  
- <span data-ttu-id="ad3de-172">暗号化テキスト</span><span class="sxs-lookup"><span data-stu-id="ad3de-172">Cipher text</span></span>  
  
 <span data-ttu-id="ad3de-173">キーと IV の長さを使用すると、暗号化パッケージのすべての部分の開始点と長さを決定することができます。これを使用してファイルを復号化します。</span><span class="sxs-lookup"><span data-stu-id="ad3de-173">You can use the lengths of the key and IV to determine the starting points and lengths of all parts of the encryption package, which can then be used to decrypt the file.</span></span>  
  
 <span data-ttu-id="ad3de-174">次のコードを [`Encrypt File`] ボタン (`buttonEncryptFile_Click`) の `Click` イベント ハンドラーとして追加します。</span><span class="sxs-lookup"><span data-stu-id="ad3de-174">Add the following code as the `Click` event handler for the `Encrypt File` button (`buttonEncryptFile_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#3)]
 [!code-vb[CryptoWalkThru#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#3)]  
  
 <span data-ttu-id="ad3de-175">フォームに次の `EncryptFile` メソッドを追加します。</span><span class="sxs-lookup"><span data-stu-id="ad3de-175">Add the following `EncryptFile` method to the form.</span></span>  
  
 [!code-csharp[CryptoWalkThru#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#5)]
 [!code-vb[CryptoWalkThru#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#5)]  
  
## <a name="decrypting-a-file"></a><span data-ttu-id="ad3de-176">ファイルの復号化</span><span class="sxs-lookup"><span data-stu-id="ad3de-176">Decrypting a File</span></span>  
 <span data-ttu-id="ad3de-177">このタスクには、[`Decrypt File`] ボタン (`buttonDecryptFile_Click`) のイベント ハンドラー メソッドと `DecryptFile` メソッドという 2 つのメソッドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ad3de-177">This task involves two methods, the event handler method for the `Decrypt File` button (`buttonDecryptFile_Click`), and the `DecryptFile` method.</span></span> <span data-ttu-id="ad3de-178">最初のメソッドは、ファイルを選択するためのダイアログ ボックスを表示し、復号化を実行する 2 番目のメソッドにファイル名を渡します。</span><span class="sxs-lookup"><span data-stu-id="ad3de-178">The first method displays a dialog box for selecting a file and passes its file name to the second method, which performs the decryption.</span></span>  
  
 <span data-ttu-id="ad3de-179">`Decrypt` メソッドは以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="ad3de-179">The `Decrypt` method does the following:</span></span>  
  
1. <span data-ttu-id="ad3de-180">コンテンツを復号化する <xref:System.Security.Cryptography.RijndaelManaged> の対称アルゴリズムを作成します。</span><span class="sxs-lookup"><span data-stu-id="ad3de-180">Creates a <xref:System.Security.Cryptography.RijndaelManaged> symmetric algorithm to decrypt the content.</span></span>  
  
2. <span data-ttu-id="ad3de-181">暗号化されたキーと IV の長さを取得するには、暗号化パッケージの <xref:System.IO.FileStream> の最初の 8 バイトを読み取ってバイト配列にします。</span><span class="sxs-lookup"><span data-stu-id="ad3de-181">Reads the first eight bytes of the <xref:System.IO.FileStream> of the encrypted package into byte arrays to obtain the lengths of the encrypted key and the IV.</span></span>  
  
3. <span data-ttu-id="ad3de-182">キーと IV を暗号化パッケージから抽出してバイト配列にします。</span><span class="sxs-lookup"><span data-stu-id="ad3de-182">Extracts the key and IV from the encryption package into byte arrays.</span></span>  
  
4. <span data-ttu-id="ad3de-183"><xref:System.Security.Cryptography.RijndaelManaged> キーを復号化する <xref:System.Security.Cryptography.RSACryptoServiceProvider> オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="ad3de-183">Creates an <xref:System.Security.Cryptography.RSACryptoServiceProvider> object to decrypt the <xref:System.Security.Cryptography.RijndaelManaged> key.</span></span>  
  
5. <span data-ttu-id="ad3de-184"><xref:System.Security.Cryptography.CryptoStream> オブジェクトを使用して、<xref:System.IO.FileStream> の暗号化パッケージの暗号テキスト セクションをバイトのブロックで読み取って復号化し、復号化されたファイルの <xref:System.IO.FileStream> オブジェクトにします。</span><span class="sxs-lookup"><span data-stu-id="ad3de-184">Uses a <xref:System.Security.Cryptography.CryptoStream> object to read and decrypt the cipher text section of the <xref:System.IO.FileStream> encryption package, in blocks of bytes, into the <xref:System.IO.FileStream> object for the decrypted file.</span></span> <span data-ttu-id="ad3de-185">これが終了すると、復号化は完了です。</span><span class="sxs-lookup"><span data-stu-id="ad3de-185">When this is finished, the decryption is completed.</span></span>  
  
 <span data-ttu-id="ad3de-186">次のコードを、[`Decrypt File`] ボタンの `Click` イベント ハンドラーとして追加します。</span><span class="sxs-lookup"><span data-stu-id="ad3de-186">Add the following code as the `Click` event handler for the `Decrypt File` button.</span></span>  
  
 [!code-csharp[CryptoWalkThru#4](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#4)]
 [!code-vb[CryptoWalkThru#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#4)]  
  
 <span data-ttu-id="ad3de-187">フォームに次の `DecryptFile` メソッドを追加します。</span><span class="sxs-lookup"><span data-stu-id="ad3de-187">Add the following `DecryptFile` method to the form.</span></span>  
  
 [!code-csharp[CryptoWalkThru#6](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#6)]
 [!code-vb[CryptoWalkThru#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#6)]  
  
## <a name="exporting-a-public-key"></a><span data-ttu-id="ad3de-188">公開キーのエクスポート</span><span class="sxs-lookup"><span data-stu-id="ad3de-188">Exporting a Public Key</span></span>  
 <span data-ttu-id="ad3de-189">この作業では、[`Create Keys`] ボタンによって作成されたキーをファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="ad3de-189">This task saves the key created by the `Create Keys` button to a file.</span></span> <span data-ttu-id="ad3de-190">パブリック パラメーターのみがエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="ad3de-190">It exports only the public parameters.</span></span>  
  
 <span data-ttu-id="ad3de-191">このタスクでは、アリスがボブに公開キーを与えるシナリオをシミュレーションします。そうすることで、ボブはアリスのファイルを暗号化できるようになります。</span><span class="sxs-lookup"><span data-stu-id="ad3de-191">This task simulates the scenario of Alice giving Bob her public key so that he can encrypt files for her.</span></span> <span data-ttu-id="ad3de-192">ボブとその公開キーを持つ他のユーザーはファイルを復号化できなくなります。彼らはプライベート パラメーターを持つ完全なキーのペアを持っていないためです。</span><span class="sxs-lookup"><span data-stu-id="ad3de-192">He and others who have that public key will not be able to decrypt them because they do not have the full key pair with private parameters.</span></span>  
  
 <span data-ttu-id="ad3de-193">次のコードを [`Export Public Key`] ボタン (`buttonExportPublicKey_Click`) の `Click` イベント ハンドラーとして追加します。</span><span class="sxs-lookup"><span data-stu-id="ad3de-193">Add the following code as the `Click` event handler for the `Export Public Key` button (`buttonExportPublicKey_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#8](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#8)]
 [!code-vb[CryptoWalkThru#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#8)]  
  
## <a name="importing-a-public-key"></a><span data-ttu-id="ad3de-194">公開キーのインポート</span><span class="sxs-lookup"><span data-stu-id="ad3de-194">Importing a Public Key</span></span>  
 <span data-ttu-id="ad3de-195">このタスクでは、[`Export Public Key`] ボタンによって作成されたパブリック パラメーターのみを持つキーを読み込み、キー コンテナー名として設定します。</span><span class="sxs-lookup"><span data-stu-id="ad3de-195">This task loads the key with only public parameters, as created by the `Export Public Key` button, and sets it as the key container name.</span></span>  
  
 <span data-ttu-id="ad3de-196">この作業では、ボブがアリスのファイルを暗号化できるように、ボブがパブリック パラメーターのみを持つアリスのキーを読み込むシナリオをシミュレーションします。</span><span class="sxs-lookup"><span data-stu-id="ad3de-196">This task simulates the scenario of Bob loading Alice's key with only public parameters so he can encrypt files for her.</span></span>  
  
 <span data-ttu-id="ad3de-197">次のコードを [`Import Public Key`] ボタン (`buttonImportPublicKey_Click`) の `Click` イベント ハンドラーとして追加します。</span><span class="sxs-lookup"><span data-stu-id="ad3de-197">Add the following code as the `Click` event handler for the `Import Public Key` button (`buttonImportPublicKey_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#9](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#9)]
 [!code-vb[CryptoWalkThru#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#9)]  
  
## <a name="getting-a-private-key"></a><span data-ttu-id="ad3de-198">秘密キーの取得</span><span class="sxs-lookup"><span data-stu-id="ad3de-198">Getting a Private Key</span></span>  
 <span data-ttu-id="ad3de-199">この作業では、[`Create Keys`] ボタンを使用して作成されたキーの名前にキー コンテナー名を設定します。</span><span class="sxs-lookup"><span data-stu-id="ad3de-199">This task sets the key container name to the name of the key created by using the `Create Keys` button.</span></span> <span data-ttu-id="ad3de-200">キー コンテナーには、プライベート パラメーターを持つ完全なキーのペアが格納されます。</span><span class="sxs-lookup"><span data-stu-id="ad3de-200">The key container will contain the full key pair with private parameters.</span></span>  
  
 <span data-ttu-id="ad3de-201">この作業では、アリスが自分の秘密キーを使用してボブが暗号化したファイルを復号化するシナリオをシミュレーションします。</span><span class="sxs-lookup"><span data-stu-id="ad3de-201">This task simulates the scenario of Alice using her private key to decrypt files encrypted by Bob.</span></span>  
  
 <span data-ttu-id="ad3de-202">次のコードを [`Get Private Key`] ボタン (`buttonGetPrivateKey_Click`) の `Click` イベント ハンドラーとして追加します。</span><span class="sxs-lookup"><span data-stu-id="ad3de-202">Add the following code as the `Click` event handler for the `Get Private Key` button (`buttonGetPrivateKey_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#7](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#7)]
 [!code-vb[CryptoWalkThru#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#7)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="ad3de-203">アプリケーションのテスト</span><span class="sxs-lookup"><span data-stu-id="ad3de-203">Testing the Application</span></span>  
 <span data-ttu-id="ad3de-204">アプリケーションをビルドしたら、次のテスト シナリオを実行します。</span><span class="sxs-lookup"><span data-stu-id="ad3de-204">After you have built the application, perform the following testing scenarios.</span></span>  
  
#### <a name="to-create-keys-encrypt-and-decrypt"></a><span data-ttu-id="ad3de-205">キーの作成、暗号化、および復号化を行うには</span><span class="sxs-lookup"><span data-stu-id="ad3de-205">To create keys, encrypt, and decrypt</span></span>  
  
1. <span data-ttu-id="ad3de-206">[`Create Keys`] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad3de-206">Click the `Create Keys` button.</span></span> <span data-ttu-id="ad3de-207">ラベルはキー名を表示し、完全なキーのペアであることを示します。</span><span class="sxs-lookup"><span data-stu-id="ad3de-207">The label displays the key name and shows that it is a full key pair.</span></span>  
  
2. <span data-ttu-id="ad3de-208">[`Export Public Key`] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad3de-208">Click the `Export Public Key` button.</span></span> <span data-ttu-id="ad3de-209">公開キーのパラメーターのエクスポートにより現在のキーは変更されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ad3de-209">Note that exporting the public key parameters does not change the current key.</span></span>  
  
3. <span data-ttu-id="ad3de-210">[`Encrypt File`] ボタンをクリックして、ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="ad3de-210">Click the `Encrypt File` button and select a file.</span></span>  
  
4. <span data-ttu-id="ad3de-211">[`Decrypt File`] ボタンをクリックし、暗号化したファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="ad3de-211">Click the `Decrypt File` button and select the file just encrypted.</span></span>  
  
5. <span data-ttu-id="ad3de-212">復号化したファイルを調べます。</span><span class="sxs-lookup"><span data-stu-id="ad3de-212">Examine the file just decrypted.</span></span>  
  
6. <span data-ttu-id="ad3de-213">次のシナリオで保持されたキー コンテナーを取得するテストを実行するには、アプリケーションを閉じて再起動します。</span><span class="sxs-lookup"><span data-stu-id="ad3de-213">Close the application and restart it to test retrieving persisted key containers in the next scenario.</span></span>  
  
#### <a name="to-encrypt-using-the-public-key"></a><span data-ttu-id="ad3de-214">公開キーを使用して暗号化するには</span><span class="sxs-lookup"><span data-stu-id="ad3de-214">To encrypt using the public key</span></span>  
  
1. <span data-ttu-id="ad3de-215">[`Import Public Key`] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad3de-215">Click the `Import Public Key` button.</span></span> <span data-ttu-id="ad3de-216">ラベルはキー名を表示し、公開キーのみであることを示します。</span><span class="sxs-lookup"><span data-stu-id="ad3de-216">The label displays the key name and shows that it is public only.</span></span>  
  
2. <span data-ttu-id="ad3de-217">[`Encrypt File`] ボタンをクリックして、ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="ad3de-217">Click the `Encrypt File` button and select a file.</span></span>  
  
3. <span data-ttu-id="ad3de-218">[`Decrypt File`] ボタンをクリックし、暗号化したファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="ad3de-218">Click the `Decrypt File` button and select the file just encrypted.</span></span> <span data-ttu-id="ad3de-219">復号化するには秘密キーが必要であるため、これは失敗します。</span><span class="sxs-lookup"><span data-stu-id="ad3de-219">This will fail because you must have the private key to decrypt.</span></span>  
  
 <span data-ttu-id="ad3de-220">このシナリオでは、公開キーのみによる別のユーザーのファイルの暗号化をデモンストレーションします。</span><span class="sxs-lookup"><span data-stu-id="ad3de-220">This scenario demonstrates having only the public key to encrypt a file for another person.</span></span> <span data-ttu-id="ad3de-221">通常、そのユーザーは公開キーのみを与え、秘密キーは復号化のため与えないでおきます。</span><span class="sxs-lookup"><span data-stu-id="ad3de-221">Typically that person would give you only the public key and withhold the private key for decryption.</span></span>  
  
#### <a name="to-decrypt-using-the-private-key"></a><span data-ttu-id="ad3de-222">秘密キーを使用して復号化するには</span><span class="sxs-lookup"><span data-stu-id="ad3de-222">To decrypt using the private key</span></span>  
  
1. <span data-ttu-id="ad3de-223">[`Get Private Key`] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad3de-223">Click the `Get Private Key` button.</span></span> <span data-ttu-id="ad3de-224">ラベルはキー名を表示し、完全なキーのペアであるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="ad3de-224">The label displays the key name and shows whether it is the full key pair.</span></span>  
  
2. <span data-ttu-id="ad3de-225">[`Decrypt File`] ボタンをクリックし、暗号化したファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="ad3de-225">Click the `Decrypt File` button and select the file just encrypted.</span></span> <span data-ttu-id="ad3de-226">復号化するための完全なキーのペアがあるため、これは成功します。</span><span class="sxs-lookup"><span data-stu-id="ad3de-226">This will be successful because you have the full key pair to decrypt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad3de-227">関連項目</span><span class="sxs-lookup"><span data-stu-id="ad3de-227">See also</span></span>

- [<span data-ttu-id="ad3de-228">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="ad3de-228">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)
