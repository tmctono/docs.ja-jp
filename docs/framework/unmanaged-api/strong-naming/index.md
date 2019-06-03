---
title: 厳密な名前付け (アンマネージ API リファレンス)
ms.date: 03/30/2017
helpviewer_keywords:
- strong naming [.NET Framework], using the unmanaged API
- native API reference [.NET Framework], strong naming
- unmanaged API reference [.NET Framework], strong naming
ms.assetid: 428c68b6-a7b4-44be-b280-75905f46612c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 45f3e8533bf7400566304ddb0fdd9d8e5a9b4280
ms.sourcegitcommit: 518e7634b86d3980ec7da5f8c308cc1054daedb7
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2019
ms.locfileid: "66456138"
---
# <a name="strong-naming-unmanaged-api-reference"></a><span data-ttu-id="5a25c-102">厳密な名前付け (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="5a25c-102">Strong Naming (Unmanaged API Reference)</span></span>
<span data-ttu-id="5a25c-103">厳密な名前付け API を使用すると、アセンブリに対する厳密な名前の署名をクライアントで管理できます。</span><span class="sxs-lookup"><span data-stu-id="5a25c-103">The strong naming API enables a client to administer strong name signing for assemblies.</span></span>  
  
 <span data-ttu-id="5a25c-104">厳密な名前を使用してアセンブリに署名すると、アセンブリ マニフェストを格納しているファイルに公開キー暗号化が追加されます。</span><span class="sxs-lookup"><span data-stu-id="5a25c-104">Signing an assembly with a strong name adds a public key encryption to the file containing the assembly manifest.</span></span> <span data-ttu-id="5a25c-105">厳密な名前による署名では、名前の一意性の検証を支援し、名前の悪用を防止し、参照が解決されたときに呼び出し元に一意の ID を提供できます。</span><span class="sxs-lookup"><span data-stu-id="5a25c-105">Strong name signing helps verify name uniqueness, prevents name spoofing, and provides callers with a unique identity when a reference is resolved.</span></span> <span data-ttu-id="5a25c-106">しかし、厳密な名前に信頼性のレベルは関連付けられていません。</span><span class="sxs-lookup"><span data-stu-id="5a25c-106">However, no level of trust is associated with a strong name.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5a25c-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="5a25c-107">In This Section</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5a25c-108">[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] 以降、これらの関数すべてが非推奨となりました。</span><span class="sxs-lookup"><span data-stu-id="5a25c-108">All of these functions have been deprecated starting with the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="5a25c-109">推奨されている代わりの関数については、[ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md) インターフェイスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a25c-109">For suggested alternatives, see the [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md) interface.</span></span>  
  
 [<span data-ttu-id="5a25c-110">GetHashFromAssemblyFile 関数</span><span class="sxs-lookup"><span data-stu-id="5a25c-110">GetHashFromAssemblyFile Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromassemblyfile-function.md)  
 <span data-ttu-id="5a25c-111">指定したハッシュ アルゴリズムを使用して、指定したアセンブリ ファイルのハッシュ値が取得されます。</span><span class="sxs-lookup"><span data-stu-id="5a25c-111">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span> <span data-ttu-id="5a25c-112">.NET Framework 4 以降では非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="5a25c-112">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="5a25c-113">GetHashFromAssemblyFileW 関数</span><span class="sxs-lookup"><span data-stu-id="5a25c-113">GetHashFromAssemblyFileW Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromassemblyfilew-function.md)  
 <span data-ttu-id="5a25c-114">指定したハッシュ アルゴリズムを使用して、Unicode 文字列として指定したアセンブリ ファイルのハッシュ値が取得されます。</span><span class="sxs-lookup"><span data-stu-id="5a25c-114">Gets a hash of the assembly file specified as a Unicode string, using the specified hash algorithm.</span></span> <span data-ttu-id="5a25c-115">.NET Framework 4 以降では非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="5a25c-115">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="5a25c-116">GetHashFromBlob 関数</span><span class="sxs-lookup"><span data-stu-id="5a25c-116">GetHashFromBlob Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromblob-function.md)  
 <span data-ttu-id="5a25c-117">指定したハッシュ アルゴリズムを使用して、指定したメモリ アドレスにあるアセンブリのハッシュが取得されます。</span><span class="sxs-lookup"><span data-stu-id="5a25c-117">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span> <span data-ttu-id="5a25c-118">.NET Framework 4 以降では非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="5a25c-118">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="5a25c-119">GetHashFromFile 関数</span><span class="sxs-lookup"><span data-stu-id="5a25c-119">GetHashFromFile Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfile-function.md)  
 <span data-ttu-id="5a25c-120">指定したファイルの内容に対してハッシュが生成されます。</span><span class="sxs-lookup"><span data-stu-id="5a25c-120">Generates a hash over the contents of the specified file.</span></span>  <span data-ttu-id="5a25c-121">.NET Framework 4 以降では非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="5a25c-121">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="5a25c-122">GetHashFromFileW 関数</span><span class="sxs-lookup"><span data-stu-id="5a25c-122">GetHashFromFileW Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfilew-function.md)  
 <span data-ttu-id="5a25c-123">Unicode 文字列で指定されたファイルの内容に対してハッシュが作成されます。</span><span class="sxs-lookup"><span data-stu-id="5a25c-123">Generates a hash over the contents of the file specified by a Unicode string.</span></span> <span data-ttu-id="5a25c-124">.NET Framework 4 以降では非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="5a25c-124">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="5a25c-125">GetHashFromHandle 関数</span><span class="sxs-lookup"><span data-stu-id="5a25c-125">GetHashFromHandle Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromhandle-function.md)  
 <span data-ttu-id="5a25c-126">指定したハッシュ アルゴリズムを使用して、指定したファイル ハンドルを含むファイルの内容に対してハッシュが作成されます。</span><span class="sxs-lookup"><span data-stu-id="5a25c-126">Generates a hash over the contents of the file with the specified file handle, using the specified hash algorithm.</span></span>  <span data-ttu-id="5a25c-127">.NET Framework 4 以降では非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="5a25c-127">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="5a25c-128">StrongNameCompareAssemblies 関数</span><span class="sxs-lookup"><span data-stu-id="5a25c-128">StrongNameCompareAssemblies Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamecompareassemblies-function.md)  
 <span data-ttu-id="5a25c-129">厳密な名前の署名に基づいて 2 つのアセンブリが異なるかどうかが判定されます。</span><span class="sxs-lookup"><span data-stu-id="5a25c-129">Determines whether two assemblies differ only by their strong name signatures.</span></span> <span data-ttu-id="5a25c-130">.NET Framework 4 以降では非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="5a25c-130">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="5a25c-131">StrongNameErrorInfo 関数</span><span class="sxs-lookup"><span data-stu-id="5a25c-131">StrongNameErrorInfo Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md)  
 <span data-ttu-id="5a25c-132">厳密な名前の関数のいずれかに基づいて最後に発生したエラー コードが取得されます。</span><span class="sxs-lookup"><span data-stu-id="5a25c-132">Gets the last error code that was raised by one of the strong name functions.</span></span>  
  
 [<span data-ttu-id="5a25c-133">StrongNameFreeBuffer 関数</span><span class="sxs-lookup"><span data-stu-id="5a25c-133">StrongNameFreeBuffer Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md)  
 <span data-ttu-id="5a25c-134">[StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md)、[StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md)、または[StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md) などの厳密な名前の関数に対する前の呼び出しで割り当てられたメモリが解放されます。</span><span class="sxs-lookup"><span data-stu-id="5a25c-134">Frees memory that was allocated with a previous call to a strong name function such as [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md), or [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md).</span></span>   <span data-ttu-id="5a25c-135">.NET Framework 4 以降では非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="5a25c-135">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="5a25c-136">StrongNameGetBlob 関数</span><span class="sxs-lookup"><span data-stu-id="5a25c-136">StrongNameGetBlob Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetblob-function.md)  
 <span data-ttu-id="5a25c-137">指定したアドレスにある実行可能ファイルのバイナリ表現が、指定したバッファーに入れられます。</span><span class="sxs-lookup"><span data-stu-id="5a25c-137">Fills the specified buffer with the binary representation of the executable file at the specified address.</span></span> <span data-ttu-id="5a25c-138">.NET Framework 4 以降では非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="5a25c-138">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="5a25c-139">StrongNameGetBlobFromImage 関数</span><span class="sxs-lookup"><span data-stu-id="5a25c-139">StrongNameGetBlobFromImage Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetblobfromimage-function.md)  
 <span data-ttu-id="5a25c-140">指定したメモリ アドレスにあるアセンブリ イメージのバイナリ表現が取得されます。</span><span class="sxs-lookup"><span data-stu-id="5a25c-140">Gets a binary representation of the assembly image at the specified memory address.</span></span> <span data-ttu-id="5a25c-141">.NET Framework 4 以降では非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="5a25c-141">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="5a25c-142">StrongNameGetPublicKey 関数</span><span class="sxs-lookup"><span data-stu-id="5a25c-142">StrongNameGetPublicKey Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md)  
 <span data-ttu-id="5a25c-143">秘密/公開キーの組から公開キーが取得されます。</span><span class="sxs-lookup"><span data-stu-id="5a25c-143">Gets the public key from a private/public key pair.</span></span> <span data-ttu-id="5a25c-144">.NET Framework 4 以降では非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="5a25c-144">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="5a25c-145">StrongNameHashSize 関数</span><span class="sxs-lookup"><span data-stu-id="5a25c-145">StrongNameHashSize Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamehashsize-function.md)  
 <span data-ttu-id="5a25c-146">指定したハッシュ アルゴリズムを使用して、ハッシュに必須のバッファー サイズが取得されます。</span><span class="sxs-lookup"><span data-stu-id="5a25c-146">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  <span data-ttu-id="5a25c-147">.NET Framework 4 以降では非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="5a25c-147">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="5a25c-148">StrongNameKeyDelete 関数</span><span class="sxs-lookup"><span data-stu-id="5a25c-148">StrongNameKeyDelete Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeydelete-function.md)  
 <span data-ttu-id="5a25c-149">指定したキー コンテナーが削除されます。</span><span class="sxs-lookup"><span data-stu-id="5a25c-149">Deletes the specified key container.</span></span> <span data-ttu-id="5a25c-150">.NET Framework 4 以降では非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="5a25c-150">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="5a25c-151">StrongNameKeyGen 関数</span><span class="sxs-lookup"><span data-stu-id="5a25c-151">StrongNameKeyGen Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeygen-function.md)  
 <span data-ttu-id="5a25c-152">厳密な名前を使用するために新しい公開/秘密キーの組が作成されます。</span><span class="sxs-lookup"><span data-stu-id="5a25c-152">Creates a new public/private key pair for strong name use.</span></span>  <span data-ttu-id="5a25c-153">.NET Framework 4 以降では非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="5a25c-153">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="5a25c-154">StrongNameKeyGenEx 関数</span><span class="sxs-lookup"><span data-stu-id="5a25c-154">StrongNameKeyGenEx Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeygenex-function.md)  
 <span data-ttu-id="5a25c-155">厳密な名前を使用するために、指定したキー サイズによって新しい公開/秘密キーの組が作成されます。</span><span class="sxs-lookup"><span data-stu-id="5a25c-155">Generates a new public/private key pair with the specified key size for strong name use.</span></span> <span data-ttu-id="5a25c-156">.NET Framework 4 以降では非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="5a25c-156">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="5a25c-157">StrongNameKeyInstall 関数</span><span class="sxs-lookup"><span data-stu-id="5a25c-157">StrongNameKeyInstall Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeyinstall-function.md)  
 <span data-ttu-id="5a25c-158">公開/秘密キーの組がコンテナーにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="5a25c-158">Imports a public/private key pair into a container.</span></span>  <span data-ttu-id="5a25c-159">.NET Framework 4 以降では非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="5a25c-159">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="5a25c-160">StrongNameSignatureGeneration 関数</span><span class="sxs-lookup"><span data-stu-id="5a25c-160">StrongNameSignatureGeneration Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)  
 <span data-ttu-id="5a25c-161">指定したアセンブリに対して厳密な名前の署名が生成されます。</span><span class="sxs-lookup"><span data-stu-id="5a25c-161">Generates a strong name signature for the specified assembly.</span></span>   <span data-ttu-id="5a25c-162">.NET Framework 4 以降では非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="5a25c-162">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="5a25c-163">StrongNameSignatureGenerationEx 関数</span><span class="sxs-lookup"><span data-stu-id="5a25c-163">StrongNameSignatureGenerationEx Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegenerationex-function.md)  
 <span data-ttu-id="5a25c-164">指定したフラグに基づいて、指定したアセンブリに対する厳密な名前の署名が作成されます。</span><span class="sxs-lookup"><span data-stu-id="5a25c-164">Generates a strong name signature for the specified assembly, based on the specified flags.</span></span>    <span data-ttu-id="5a25c-165">.NET Framework 4 以降では非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="5a25c-165">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="5a25c-166">StrongNameSignatureSize 関数</span><span class="sxs-lookup"><span data-stu-id="5a25c-166">StrongNameSignatureSize Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturesize-function.md)  
 <span data-ttu-id="5a25c-167">厳密な名前の署名のサイズが返されます。</span><span class="sxs-lookup"><span data-stu-id="5a25c-167">Returns the size of the strong name signature.</span></span> <span data-ttu-id="5a25c-168">.NET Framework 4 以降では非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="5a25c-168">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="5a25c-169">StrongNameSignatureVerification 関数</span><span class="sxs-lookup"><span data-stu-id="5a25c-169">StrongNameSignatureVerification Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverification-function.md)  
 <span data-ttu-id="5a25c-170">指定したパスにあるアセンブリ マニフェストに厳密な名前の署名が含まれるかどうかを示す値が取得されます。これは指定したフラグに従って確認されます。</span><span class="sxs-lookup"><span data-stu-id="5a25c-170">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature, which is verified according to the specified flags.</span></span> <span data-ttu-id="5a25c-171">.NET Framework 4 以降では非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="5a25c-171">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="5a25c-172">StrongNameSignatureVerificationEx 関数</span><span class="sxs-lookup"><span data-stu-id="5a25c-172">StrongNameSignatureVerificationEx Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverificationex-function.md)  
 <span data-ttu-id="5a25c-173">指定したパスにあるアセンブリ マニフェストに厳密な名前の署名が含まれるかどうかを示す値が取得されます。</span><span class="sxs-lookup"><span data-stu-id="5a25c-173">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature.</span></span>  <span data-ttu-id="5a25c-174">.NET Framework 4 以降では非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="5a25c-174">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="5a25c-175">StrongNameSignatureVerificationFromImage 関数</span><span class="sxs-lookup"><span data-stu-id="5a25c-175">StrongNameSignatureVerificationFromImage Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverificationfromimage-function.md)  
 <span data-ttu-id="5a25c-176">メモリに既にマップされているアセンブリが、関連付けられている公開キーに対して有効であるかどうかが確認されます。</span><span class="sxs-lookup"><span data-stu-id="5a25c-176">Verifies that an assembly that has already been mapped to memory is valid for the associated public key.</span></span> <span data-ttu-id="5a25c-177">.NET Framework 4 以降では非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="5a25c-177">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="5a25c-178">StrongNameTokenFromAssembly 関数</span><span class="sxs-lookup"><span data-stu-id="5a25c-178">StrongNameTokenFromAssembly Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassembly-function.md)  
 <span data-ttu-id="5a25c-179">指定したアセンブリ ファイルから、厳密な名前トークンが作成されます。</span><span class="sxs-lookup"><span data-stu-id="5a25c-179">Creates a strong name token from the specified assembly file.</span></span>  <span data-ttu-id="5a25c-180">.NET Framework 4 以降では非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="5a25c-180">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="5a25c-181">StrongNameTokenFromAssemblyEx 関数</span><span class="sxs-lookup"><span data-stu-id="5a25c-181">StrongNameTokenFromAssemblyEx Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassemblyex-function.md)  
 <span data-ttu-id="5a25c-182">指定したアセンブリ ファイルから厳密な名前のトークンが作成され、公開キーが返されます。</span><span class="sxs-lookup"><span data-stu-id="5a25c-182">Creates a strong name token from the specified assembly file, and returns the public key.</span></span> <span data-ttu-id="5a25c-183">.NET Framework 4 以降では非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="5a25c-183">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="5a25c-184">StrongNameTokenFromPublicKey 関数</span><span class="sxs-lookup"><span data-stu-id="5a25c-184">StrongNameTokenFromPublicKey Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md)  
 <span data-ttu-id="5a25c-185">公開キーを表すトークンが取得されます。</span><span class="sxs-lookup"><span data-stu-id="5a25c-185">Gets a token representing a public key.</span></span> <span data-ttu-id="5a25c-186">.NET Framework 4 以降では非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="5a25c-186">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="5a25c-187">PublicKeyBlob 構造体</span><span class="sxs-lookup"><span data-stu-id="5a25c-187">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)  
 <span data-ttu-id="5a25c-188">公開/秘密キーの組の公開キーがバイナリ形式で表されます。</span><span class="sxs-lookup"><span data-stu-id="5a25c-188">Represents the public key of a public/private key pair in binary format.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a25c-189">関連項目</span><span class="sxs-lookup"><span data-stu-id="5a25c-189">See also</span></span>

- [<span data-ttu-id="5a25c-190">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5a25c-190">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
- [<span data-ttu-id="5a25c-191">アンマネージ API リファレンス</span><span class="sxs-lookup"><span data-stu-id="5a25c-191">Unmanaged API Reference</span></span>](../../../../docs/framework/unmanaged-api/index.md)
