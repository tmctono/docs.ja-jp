---
title: EmitAssemblyCustomAttribute メソッド
ms.date: 03/30/2017
api_name:
- IALink.EmitAssemblyCustomAttribute
- EmitAssemblyCustomAttribute
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitAssemblyCustomAttribute
helpviewer_keywords:
- EmitAssemblyCustomAttribute method
ms.assetid: b72f5409-79af-4fa7-90a7-7630eec170f1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 67073f04cfe981dd383369029d9a4b436929a0a6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59117846"
---
# <a name="emitassemblycustomattribute-method"></a><span data-ttu-id="24f98-102">EmitAssemblyCustomAttribute メソッド</span><span class="sxs-lookup"><span data-stu-id="24f98-102">EmitAssemblyCustomAttribute Method</span></span>
<span data-ttu-id="24f98-103">アセンブリ レベルのカスタム属性を設定する呼び出し。</span><span class="sxs-lookup"><span data-stu-id="24f98-103">Call to set assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24f98-104">構文</span><span class="sxs-lookup"><span data-stu-id="24f98-104">Syntax</span></span>  
  
```  
HRESULT EmitAssemblyCustomAttribute(  
    mdAssembly   AssemblyID,  
    mdToken      FileToken,  
    mdToken      tkType,  
    void const*  pCustomValue,  
    DWORD        cbCustomValue,  
    BOOL         bSecurity,  
    BOOL         bAllowMulti  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="24f98-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="24f98-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="24f98-106">アセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="24f98-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="24f98-107">属性を定義するファイルです。</span><span class="sxs-lookup"><span data-stu-id="24f98-107">File that defiles the attribute.</span></span> <span data-ttu-id="24f98-108">場合に NULL が`AssemblyID`バインドされていない netmodule では示されません。</span><span class="sxs-lookup"><span data-stu-id="24f98-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `tkType`  
 <span data-ttu-id="24f98-109">カスタム属性の型。</span><span class="sxs-lookup"><span data-stu-id="24f98-109">Type of the custom attribute.</span></span>  
  
 `pCustomValue`  
 <span data-ttu-id="24f98-110">カスタム値のデータ。</span><span class="sxs-lookup"><span data-stu-id="24f98-110">Custom value data.</span></span>  
  
 `cbCustomValue`  
 <span data-ttu-id="24f98-111">カスタム値のデータの長さ。</span><span class="sxs-lookup"><span data-stu-id="24f98-111">Length of custom value data.</span></span>  
  
 `bSecurity`  
 <span data-ttu-id="24f98-112">カスタム属性がアセンブリの署名に関連する場合は TRUE。</span><span class="sxs-lookup"><span data-stu-id="24f98-112">TRUE if the custom attribute is related to assembly signing.</span></span>  
  
 `bAllowMulti`  
 <span data-ttu-id="24f98-113">複数の属性が出力する場合は TRUE。</span><span class="sxs-lookup"><span data-stu-id="24f98-113">TRUE if multiple attributes are to be emitted.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="24f98-114">戻り値</span><span class="sxs-lookup"><span data-stu-id="24f98-114">Return Value</span></span>  
 <span data-ttu-id="24f98-115">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="24f98-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24f98-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="24f98-116">Requirements</span></span>  
 <span data-ttu-id="24f98-117">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="24f98-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24f98-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="24f98-118">See also</span></span>

- [<span data-ttu-id="24f98-119">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="24f98-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="24f98-120">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="24f98-120">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="24f98-121">ALink API</span><span class="sxs-lookup"><span data-stu-id="24f98-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
