---
title: ICeeGen インターフェイス
ms.date: 03/30/2017
api_name:
- ICeeGen
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen
helpviewer_keywords:
- ICeeGen interface [.NET Framework metadata]
ms.assetid: 383d20b0-efe9-4e71-8fb8-1186b2e7d0c0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6fb081c48abf899b44da1c1351efa3f6036f1c8d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59176125"
---
# <a name="iceegen-interface"></a><span data-ttu-id="f0c8c-102">ICeeGen インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f0c8c-102">ICeeGen Interface</span></span>
<span data-ttu-id="f0c8c-103">動的なコード コンパイルのためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="f0c8c-103">Provides methods for dynamic code compilation.</span></span>  
  
 <span data-ttu-id="f0c8c-104">このインターフェイスは廃止され、使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0c8c-104">This interface is obsolete and should not be used.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f0c8c-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="f0c8c-105">Methods</span></span>  
  
|<span data-ttu-id="f0c8c-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="f0c8c-106">Method</span></span>|<span data-ttu-id="f0c8c-107">説明</span><span class="sxs-lookup"><span data-stu-id="f0c8c-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f0c8c-108">AddSectionReloc メソッド</span><span class="sxs-lookup"><span data-stu-id="f0c8c-108">AddSectionReloc Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)|<span data-ttu-id="f0c8c-109">互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="f0c8c-109">Obsolete.</span></span> <span data-ttu-id="f0c8c-110">コード ベースを .reloc 命令を追加します。</span><span class="sxs-lookup"><span data-stu-id="f0c8c-110">Adds a .reloc instruction to the code base.</span></span>|  
|[<span data-ttu-id="f0c8c-111">AllocateMethodBuffer メソッド</span><span class="sxs-lookup"><span data-stu-id="f0c8c-111">AllocateMethodBuffer Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-allocatemethodbuffer-method.md)|<span data-ttu-id="f0c8c-112">互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="f0c8c-112">Obsolete.</span></span> <span data-ttu-id="f0c8c-113">メソッドで指定されたサイズのバッファーを作成し、メソッドの相対仮想アドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="f0c8c-113">Creates a buffer of the specified size for a method, and gets the relative virtual address of the method.</span></span>|  
|[<span data-ttu-id="f0c8c-114">ComputePointer メソッド</span><span class="sxs-lookup"><span data-stu-id="f0c8c-114">ComputePointer Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-computepointer-method.md)|<span data-ttu-id="f0c8c-115">互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="f0c8c-115">Obsolete.</span></span> <span data-ttu-id="f0c8c-116">指定したコードのセクションのバッファーを決定します。</span><span class="sxs-lookup"><span data-stu-id="f0c8c-116">Determines the buffer for the specified code section.</span></span>|  
|[<span data-ttu-id="f0c8c-117">EmitString メソッド</span><span class="sxs-lookup"><span data-stu-id="f0c8c-117">EmitString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-emitstring-method.md)|<span data-ttu-id="f0c8c-118">互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="f0c8c-118">Obsolete.</span></span> <span data-ttu-id="f0c8c-119">コード ベースに、指定した文字列を出力します。</span><span class="sxs-lookup"><span data-stu-id="f0c8c-119">Emits the specified string into the code base.</span></span>|  
|[<span data-ttu-id="f0c8c-120">GenerateCeeFile メソッド</span><span class="sxs-lookup"><span data-stu-id="f0c8c-120">GenerateCeeFile Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-generateceefile-method.md)|<span data-ttu-id="f0c8c-121">互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="f0c8c-121">Obsolete.</span></span> <span data-ttu-id="f0c8c-122">これに現在読み込まれてコード ベースを含むコード ベースのファイルが生成されます`ICeeGen`します。</span><span class="sxs-lookup"><span data-stu-id="f0c8c-122">Generates a code-base file that contains the code base currently loaded into this `ICeeGen`.</span></span>|  
|[<span data-ttu-id="f0c8c-123">GenerateCeeMemoryImage メソッド</span><span class="sxs-lookup"><span data-stu-id="f0c8c-123">GenerateCeeMemoryImage Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-generateceememoryimage-method.md)|<span data-ttu-id="f0c8c-124">互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="f0c8c-124">Obsolete.</span></span> <span data-ttu-id="f0c8c-125">コード ベースのメモリ内には、イメージを生成します。</span><span class="sxs-lookup"><span data-stu-id="f0c8c-125">Generates an image in memory for the code base.</span></span>|  
|[<span data-ttu-id="f0c8c-126">GetIlSection メソッド</span><span class="sxs-lookup"><span data-stu-id="f0c8c-126">GetIlSection Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getilsection-method.md)|<span data-ttu-id="f0c8c-127">互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="f0c8c-127">Obsolete.</span></span> <span data-ttu-id="f0c8c-128">指定したハンドルによって参照される基本の中間言語コードのセクションを取得します。</span><span class="sxs-lookup"><span data-stu-id="f0c8c-128">Gets the section of the intermediate language code base referenced by the specified handle.</span></span>|  
|[<span data-ttu-id="f0c8c-129">GetIMapTokenIface メソッド</span><span class="sxs-lookup"><span data-stu-id="f0c8c-129">GetIMapTokenIface Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getimaptokeniface-method.md)|<span data-ttu-id="f0c8c-130">互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="f0c8c-130">Obsolete.</span></span> <span data-ttu-id="f0c8c-131">指定したトークンによって参照されているインターフェイスを取得します。</span><span class="sxs-lookup"><span data-stu-id="f0c8c-131">Gets the interface referenced by the specified token.</span></span>|  
|[<span data-ttu-id="f0c8c-132">GetMethodBuffer メソッド</span><span class="sxs-lookup"><span data-stu-id="f0c8c-132">GetMethodBuffer Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getmethodbuffer-method.md)|<span data-ttu-id="f0c8c-133">互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="f0c8c-133">Obsolete.</span></span> <span data-ttu-id="f0c8c-134">指定の相対仮想アドレスにあるメソッドの適切なサイズのバッファーを取得します。</span><span class="sxs-lookup"><span data-stu-id="f0c8c-134">Gets a buffer of the appropriate size for the method at the specified relative virtual address.</span></span>|  
|[<span data-ttu-id="f0c8c-135">GetSectionBlock メソッド</span><span class="sxs-lookup"><span data-stu-id="f0c8c-135">GetSectionBlock Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectionblock-method.md)|<span data-ttu-id="f0c8c-136">互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="f0c8c-136">Obsolete.</span></span> <span data-ttu-id="f0c8c-137">コード ベースのセクションのブロックを取得します。</span><span class="sxs-lookup"><span data-stu-id="f0c8c-137">Gets a section block of the code base.</span></span>|  
|[<span data-ttu-id="f0c8c-138">GetSectionCreate メソッド</span><span class="sxs-lookup"><span data-stu-id="f0c8c-138">GetSectionCreate Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectioncreate-method.md)|<span data-ttu-id="f0c8c-139">互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="f0c8c-139">Obsolete.</span></span> <span data-ttu-id="f0c8c-140">生成し、指定した名前とフラグの値を使用してコードのセクションを取得します。</span><span class="sxs-lookup"><span data-stu-id="f0c8c-140">Generates and gets a code section using the specified name and flag values.</span></span>|  
|[<span data-ttu-id="f0c8c-141">GetSectionDataLen メソッド</span><span class="sxs-lookup"><span data-stu-id="f0c8c-141">GetSectionDataLen Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectiondatalen-method.md)|<span data-ttu-id="f0c8c-142">互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="f0c8c-142">Obsolete.</span></span> <span data-ttu-id="f0c8c-143">指定されたセクションの長さを取得します。</span><span class="sxs-lookup"><span data-stu-id="f0c8c-143">Gets the length of the specified section.</span></span>|  
|[<span data-ttu-id="f0c8c-144">GetString メソッド</span><span class="sxs-lookup"><span data-stu-id="f0c8c-144">GetString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getstring-method.md)|<span data-ttu-id="f0c8c-145">互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="f0c8c-145">Obsolete.</span></span> <span data-ttu-id="f0c8c-146">指定された相対仮想アドレスに格納されている文字列を取得します。</span><span class="sxs-lookup"><span data-stu-id="f0c8c-146">Gets the string stored at the specified relative virtual address.</span></span>|  
|[<span data-ttu-id="f0c8c-147">GetStringSection メソッド</span><span class="sxs-lookup"><span data-stu-id="f0c8c-147">GetStringSection Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getstringsection-method.md)|<span data-ttu-id="f0c8c-148">互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="f0c8c-148">Obsolete.</span></span> <span data-ttu-id="f0c8c-149">指定したハンドルによって参照されるコードのセクションの文字列表現を取得します。</span><span class="sxs-lookup"><span data-stu-id="f0c8c-149">Gets a string representation of the code section referenced by the specified handle.</span></span>|  
|[<span data-ttu-id="f0c8c-150">TruncateSection メソッド</span><span class="sxs-lookup"><span data-stu-id="f0c8c-150">TruncateSection Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-truncatesection-method.md)|<span data-ttu-id="f0c8c-151">互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="f0c8c-151">Obsolete.</span></span> <span data-ttu-id="f0c8c-152">指定された長さでは、指定したコードのセクションを切り捨てます。</span><span class="sxs-lookup"><span data-stu-id="f0c8c-152">Truncates the specified code section by the specified length.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f0c8c-153">必要条件</span><span class="sxs-lookup"><span data-stu-id="f0c8c-153">Requirements</span></span>  
 <span data-ttu-id="f0c8c-154">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0c8c-154">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0c8c-155">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f0c8c-155">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f0c8c-156">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="f0c8c-156">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="f0c8c-157">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="f0c8c-157">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f0c8c-158">関連項目</span><span class="sxs-lookup"><span data-stu-id="f0c8c-158">See also</span></span>

- [<span data-ttu-id="f0c8c-159">メタデータ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f0c8c-159">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
