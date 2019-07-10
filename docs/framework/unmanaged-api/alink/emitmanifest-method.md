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
ms.openlocfilehash: 91dc4cb7d64d49d1e95c0c8eb79a29736559d842
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742086"
---
# <a name="emitmanifest-method"></a><span data-ttu-id="43e9f-102">EmitManifest メソッド</span><span class="sxs-lookup"><span data-stu-id="43e9f-102">EmitManifest Method</span></span>
<span data-ttu-id="43e9f-103">最終的なマニフェストを出力します。</span><span class="sxs-lookup"><span data-stu-id="43e9f-103">Emits the final manifest.</span></span> <span data-ttu-id="43e9f-104">その他のすべてのファイルをインポートし、すべてのオプションを設定した後、このメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="43e9f-104">Call this method after importing all other files and setting all options.</span></span> <span data-ttu-id="43e9f-105">非バインド モジュールのこのメソッドを呼び出さないでください。</span><span class="sxs-lookup"><span data-stu-id="43e9f-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43e9f-106">構文</span><span class="sxs-lookup"><span data-stu-id="43e9f-106">Syntax</span></span>  
  
```cpp  
HRESULT EmitManifest(  
    mdAssembly   AssemblyID,  
    DWORD*       pdwReserveSize,  
    mdAssembly*  ptkManifest  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="43e9f-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="43e9f-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="43e9f-108">アセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="43e9f-108">ID of the assembly.</span></span>  
  
 `pdwReserveSize`  
 <span data-ttu-id="43e9f-109">取得したアセンブリ ファイルで予約サイズを受け取る[StrongNameSignatureSize 関数](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturesize-function.md)します。</span><span class="sxs-lookup"><span data-stu-id="43e9f-109">Receives the size to reserve in the assembly file, retrieved from [StrongNameSignatureSize Function](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturesize-function.md).</span></span>  
  
 `ptkManifest`  
 <span data-ttu-id="43e9f-110">必要に応じて、アセンブリのマニフェスト トークンを受信します。</span><span class="sxs-lookup"><span data-stu-id="43e9f-110">Optionally receives the assembly manifest token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="43e9f-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="43e9f-111">Return Value</span></span>  
 <span data-ttu-id="43e9f-112">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="43e9f-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43e9f-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="43e9f-113">Requirements</span></span>  
 <span data-ttu-id="43e9f-114">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="43e9f-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43e9f-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="43e9f-115">See also</span></span>

- [<span data-ttu-id="43e9f-116">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="43e9f-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="43e9f-117">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="43e9f-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="43e9f-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="43e9f-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
