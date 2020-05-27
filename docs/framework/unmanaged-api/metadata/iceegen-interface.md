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
ms.openlocfilehash: e6cf0aa6f731d0a417e1a2be0ca1d0f8c9299379
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008275"
---
# <a name="iceegen-interface"></a><span data-ttu-id="229a1-102">ICeeGen インターフェイス</span><span class="sxs-lookup"><span data-stu-id="229a1-102">ICeeGen Interface</span></span>
<span data-ttu-id="229a1-103">動的なコード コンパイルのためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="229a1-103">Provides methods for dynamic code compilation.</span></span>  
  
 <span data-ttu-id="229a1-104">このインターフェイスは互換性のために残されています。使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="229a1-104">This interface is obsolete and should not be used.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="229a1-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="229a1-105">Methods</span></span>  
  
|<span data-ttu-id="229a1-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="229a1-106">Method</span></span>|<span data-ttu-id="229a1-107">説明</span><span class="sxs-lookup"><span data-stu-id="229a1-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="229a1-108">AddSectionReloc メソッド</span><span class="sxs-lookup"><span data-stu-id="229a1-108">AddSectionReloc Method</span></span>](iceegen-addsectionreloc-method.md)|<span data-ttu-id="229a1-109">互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="229a1-109">Obsolete.</span></span> <span data-ttu-id="229a1-110">コードベースに reloc 命令を追加します。</span><span class="sxs-lookup"><span data-stu-id="229a1-110">Adds a .reloc instruction to the code base.</span></span>|  
|[<span data-ttu-id="229a1-111">AllocateMethodBuffer メソッド</span><span class="sxs-lookup"><span data-stu-id="229a1-111">AllocateMethodBuffer Method</span></span>](iceegen-allocatemethodbuffer-method.md)|<span data-ttu-id="229a1-112">互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="229a1-112">Obsolete.</span></span> <span data-ttu-id="229a1-113">メソッドに対して指定したサイズのバッファーを作成し、メソッドの相対仮想アドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="229a1-113">Creates a buffer of the specified size for a method, and gets the relative virtual address of the method.</span></span>|  
|[<span data-ttu-id="229a1-114">ComputePointer メソッド</span><span class="sxs-lookup"><span data-stu-id="229a1-114">ComputePointer Method</span></span>](iceegen-computepointer-method.md)|<span data-ttu-id="229a1-115">互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="229a1-115">Obsolete.</span></span> <span data-ttu-id="229a1-116">指定されたコードセクションのバッファーを決定します。</span><span class="sxs-lookup"><span data-stu-id="229a1-116">Determines the buffer for the specified code section.</span></span>|  
|[<span data-ttu-id="229a1-117">EmitString メソッド</span><span class="sxs-lookup"><span data-stu-id="229a1-117">EmitString Method</span></span>](iceegen-emitstring-method.md)|<span data-ttu-id="229a1-118">互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="229a1-118">Obsolete.</span></span> <span data-ttu-id="229a1-119">指定した文字列をコードベースに出力します。</span><span class="sxs-lookup"><span data-stu-id="229a1-119">Emits the specified string into the code base.</span></span>|  
|[<span data-ttu-id="229a1-120">GenerateCeeFile メソッド</span><span class="sxs-lookup"><span data-stu-id="229a1-120">GenerateCeeFile Method</span></span>](iceegen-generateceefile-method.md)|<span data-ttu-id="229a1-121">互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="229a1-121">Obsolete.</span></span> <span data-ttu-id="229a1-122">このに現在読み込まれているコードベースを含むコードベースファイルを生成 `ICeeGen` します。</span><span class="sxs-lookup"><span data-stu-id="229a1-122">Generates a code-base file that contains the code base currently loaded into this `ICeeGen`.</span></span>|  
|[<span data-ttu-id="229a1-123">GenerateCeeMemoryImage メソッド</span><span class="sxs-lookup"><span data-stu-id="229a1-123">GenerateCeeMemoryImage Method</span></span>](iceegen-generateceememoryimage-method.md)|<span data-ttu-id="229a1-124">互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="229a1-124">Obsolete.</span></span> <span data-ttu-id="229a1-125">コードベースのイメージをメモリ内に生成します。</span><span class="sxs-lookup"><span data-stu-id="229a1-125">Generates an image in memory for the code base.</span></span>|  
|[<span data-ttu-id="229a1-126">GetIlSection メソッド</span><span class="sxs-lookup"><span data-stu-id="229a1-126">GetIlSection Method</span></span>](iceegen-getilsection-method.md)|<span data-ttu-id="229a1-127">互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="229a1-127">Obsolete.</span></span> <span data-ttu-id="229a1-128">指定したハンドルによって参照される中間言語コードベースのセクションを取得します。</span><span class="sxs-lookup"><span data-stu-id="229a1-128">Gets the section of the intermediate language code base referenced by the specified handle.</span></span>|  
|[<span data-ttu-id="229a1-129">GetIMapTokenIface メソッド</span><span class="sxs-lookup"><span data-stu-id="229a1-129">GetIMapTokenIface Method</span></span>](iceegen-getimaptokeniface-method.md)|<span data-ttu-id="229a1-130">互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="229a1-130">Obsolete.</span></span> <span data-ttu-id="229a1-131">指定したトークンによって参照されるインターフェイスを取得します。</span><span class="sxs-lookup"><span data-stu-id="229a1-131">Gets the interface referenced by the specified token.</span></span>|  
|[<span data-ttu-id="229a1-132">GetMethodBuffer メソッド</span><span class="sxs-lookup"><span data-stu-id="229a1-132">GetMethodBuffer Method</span></span>](iceegen-getmethodbuffer-method.md)|<span data-ttu-id="229a1-133">互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="229a1-133">Obsolete.</span></span> <span data-ttu-id="229a1-134">指定した相対仮想アドレスで、メソッドの適切なサイズのバッファーを取得します。</span><span class="sxs-lookup"><span data-stu-id="229a1-134">Gets a buffer of the appropriate size for the method at the specified relative virtual address.</span></span>|  
|[<span data-ttu-id="229a1-135">GetSectionBlock メソッド</span><span class="sxs-lookup"><span data-stu-id="229a1-135">GetSectionBlock Method</span></span>](iceegen-getsectionblock-method.md)|<span data-ttu-id="229a1-136">互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="229a1-136">Obsolete.</span></span> <span data-ttu-id="229a1-137">コードベースのセクションブロックを取得します。</span><span class="sxs-lookup"><span data-stu-id="229a1-137">Gets a section block of the code base.</span></span>|  
|[<span data-ttu-id="229a1-138">GetSectionCreate メソッド</span><span class="sxs-lookup"><span data-stu-id="229a1-138">GetSectionCreate Method</span></span>](iceegen-getsectioncreate-method.md)|<span data-ttu-id="229a1-139">互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="229a1-139">Obsolete.</span></span> <span data-ttu-id="229a1-140">指定された名前とフラグ値を使用して、コードセクションを生成して取得します。</span><span class="sxs-lookup"><span data-stu-id="229a1-140">Generates and gets a code section using the specified name and flag values.</span></span>|  
|[<span data-ttu-id="229a1-141">GetSectionDataLen メソッド</span><span class="sxs-lookup"><span data-stu-id="229a1-141">GetSectionDataLen Method</span></span>](iceegen-getsectiondatalen-method.md)|<span data-ttu-id="229a1-142">互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="229a1-142">Obsolete.</span></span> <span data-ttu-id="229a1-143">指定したセクションの長さを取得します。</span><span class="sxs-lookup"><span data-stu-id="229a1-143">Gets the length of the specified section.</span></span>|  
|[<span data-ttu-id="229a1-144">GetString メソッド</span><span class="sxs-lookup"><span data-stu-id="229a1-144">GetString Method</span></span>](iceegen-getstring-method.md)|<span data-ttu-id="229a1-145">互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="229a1-145">Obsolete.</span></span> <span data-ttu-id="229a1-146">指定した相対仮想アドレスに格納されている文字列を取得します。</span><span class="sxs-lookup"><span data-stu-id="229a1-146">Gets the string stored at the specified relative virtual address.</span></span>|  
|[<span data-ttu-id="229a1-147">GetStringSection メソッド</span><span class="sxs-lookup"><span data-stu-id="229a1-147">GetStringSection Method</span></span>](iceegen-getstringsection-method.md)|<span data-ttu-id="229a1-148">互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="229a1-148">Obsolete.</span></span> <span data-ttu-id="229a1-149">指定したハンドルによって参照されるコードセクションの文字列表現を取得します。</span><span class="sxs-lookup"><span data-stu-id="229a1-149">Gets a string representation of the code section referenced by the specified handle.</span></span>|  
|[<span data-ttu-id="229a1-150">TruncateSection メソッド</span><span class="sxs-lookup"><span data-stu-id="229a1-150">TruncateSection Method</span></span>](iceegen-truncatesection-method.md)|<span data-ttu-id="229a1-151">互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="229a1-151">Obsolete.</span></span> <span data-ttu-id="229a1-152">指定したコードセクションを指定した長さだけ切り捨てます。</span><span class="sxs-lookup"><span data-stu-id="229a1-152">Truncates the specified code section by the specified length.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="229a1-153">必要条件</span><span class="sxs-lookup"><span data-stu-id="229a1-153">Requirements</span></span>  
 <span data-ttu-id="229a1-154">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="229a1-154">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="229a1-155">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="229a1-155">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="229a1-156">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="229a1-156">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="229a1-157">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="229a1-157">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="229a1-158">関連項目</span><span class="sxs-lookup"><span data-stu-id="229a1-158">See also</span></span>

- [<span data-ttu-id="229a1-159">メタデータ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="229a1-159">Metadata Interfaces</span></span>](metadata-interfaces.md)
