---
title: EmitManifest メソッド
ms.date: 03/30/2017
api_name:
- EmitManifest
- IALink.EmitManifest
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitManifest
helpviewer_keywords:
- EmitManifest method
ms.assetid: fdebc1f3-b62e-4d9e-b775-8ccaa8ecb250
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 051b5f47db05301f3a3326a2cc4cc5cf5c8b1ec2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59137827"
---
# <a name="emitmanifest-method"></a><span data-ttu-id="b9a3a-102">EmitManifest メソッド</span><span class="sxs-lookup"><span data-stu-id="b9a3a-102">EmitManifest Method</span></span>
<span data-ttu-id="b9a3a-103">最終的なマニフェストを出力します。</span><span class="sxs-lookup"><span data-stu-id="b9a3a-103">Emits the final manifest.</span></span> <span data-ttu-id="b9a3a-104">その他のすべてのファイルをインポートし、すべてのオプションを設定した後、このメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="b9a3a-104">Call this method after importing all other files and setting all options.</span></span> <span data-ttu-id="b9a3a-105">非バインド モジュールのこのメソッドを呼び出さないでください。</span><span class="sxs-lookup"><span data-stu-id="b9a3a-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9a3a-106">構文</span><span class="sxs-lookup"><span data-stu-id="b9a3a-106">Syntax</span></span>  
  
```  
HRESULT EmitManifest(  
    mdAssembly   AssemblyID,  
    DWORD*       pdwReserveSize,  
    mdAssembly*  ptkManifest  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="b9a3a-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b9a3a-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="b9a3a-108">アセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="b9a3a-108">ID of the assembly.</span></span>  
  
 `pdwReserveSize`  
 <span data-ttu-id="b9a3a-109">取得したアセンブリ ファイルで予約サイズを受け取る[StrongNameSignatureSize 関数](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturesize-function.md)します。</span><span class="sxs-lookup"><span data-stu-id="b9a3a-109">Receives the size to reserve in the assembly file, retrieved from [StrongNameSignatureSize Function](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturesize-function.md).</span></span>  
  
 `ptkManifest`  
 <span data-ttu-id="b9a3a-110">必要に応じて、アセンブリのマニフェスト トークンを受信します。</span><span class="sxs-lookup"><span data-stu-id="b9a3a-110">Optionally receives the assembly manifest token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b9a3a-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="b9a3a-111">Return Value</span></span>  
 <span data-ttu-id="b9a3a-112">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="b9a3a-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9a3a-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="b9a3a-113">Requirements</span></span>  
 <span data-ttu-id="b9a3a-114">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="b9a3a-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9a3a-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="b9a3a-115">See also</span></span>

- [<span data-ttu-id="b9a3a-116">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b9a3a-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="b9a3a-117">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b9a3a-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="b9a3a-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="b9a3a-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
