---
title: SetPEKind メソッド
ms.date: 03/30/2017
api_name:
- IALink2.SetPEKind
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetPEKind
helpviewer_keywords:
- SetPEKind method
ms.assetid: 050e77ee-3014-45c0-9e29-2ebe29347b0d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dec04fa267c61798a3340e9d1e18150b812e9eaf
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59092657"
---
# <a name="setpekind-method"></a><span data-ttu-id="7b479-102">SetPEKind メソッド</span><span class="sxs-lookup"><span data-stu-id="7b479-102">SetPEKind Method</span></span>
<span data-ttu-id="7b479-103">コンピューター固有またはマシンに依存しないのいずれかのノートブックの実行可能ファイル タイプを決定します。</span><span class="sxs-lookup"><span data-stu-id="7b479-103">Determines the portable executable type, either machine-specific or machine-agnostic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b479-104">構文</span><span class="sxs-lookup"><span data-stu-id="7b479-104">Syntax</span></span>  
  
```  
HRESULT SetPEKind(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwPEKind,  
    DWORD dwMachine  
) PURE;   
```  
  
## <a name="parameters"></a><span data-ttu-id="7b479-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7b479-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="7b479-106">アセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="7b479-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="7b479-107">PE の種類を設定するファイルのトークン。</span><span class="sxs-lookup"><span data-stu-id="7b479-107">Token of file for which the PE type is to be set.</span></span> <span data-ttu-id="7b479-108">場合に NULL が`AssemblyID`バインドされていない netmodule では示されません。</span><span class="sxs-lookup"><span data-stu-id="7b479-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `dwPEKind`  
 <span data-ttu-id="7b479-109">示されている PE の型、 [CorPEKind 列挙型](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md)します。</span><span class="sxs-lookup"><span data-stu-id="7b479-109">The type of PE, as indicated by the [CorPEKind Enumeration](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md).</span></span>  
  
 `dwMachine`  
 <span data-ttu-id="7b479-110">ターゲット コンピューターのアーキテクチャ、NT ヘッダーに記載されています。</span><span class="sxs-lookup"><span data-stu-id="7b479-110">The target machine architecture, as indicated in the NT header.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7b479-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="7b479-111">Return Value</span></span>  
 <span data-ttu-id="7b479-112">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="7b479-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b479-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="7b479-113">Requirements</span></span>  
 <span data-ttu-id="7b479-114">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="7b479-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b479-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="7b479-115">See also</span></span>

- [<span data-ttu-id="7b479-116">GetPEKind メソッド</span><span class="sxs-lookup"><span data-stu-id="7b479-116">GetPEKind Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md)
- [<span data-ttu-id="7b479-117">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7b479-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="7b479-118">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7b479-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="7b479-119">ALink API</span><span class="sxs-lookup"><span data-stu-id="7b479-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
