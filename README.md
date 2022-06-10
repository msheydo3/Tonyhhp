<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8" />
    <link rel="stylesheet" href="https://cdn.staticfile.org/twitter-bootstrap/4.3.1/css/bootstrap.min.css">
    <script src="https://cdn.staticfile.org/jquery/3.2.1/jquery.min.js"></script>
    <script src="https://cdn.staticfile.org/popper.js/1.15.0/umd/popper.min.js"></script>
    <script src="https://cdn.staticfile.org/twitter-bootstrap/4.3.1/js/bootstrap.min.js"></script>
    <script src="http://www.jq22.com/jquery/jquery-1.10.2.js"></script>
    <script type="text/javascript" src="all.js"></script>
    <title></title>
    <style>
        .carousel-inner img {
            width: 100%;
            height: 100%;
            border-radius: 20px;
            bottom:25%;
        }

        * {
            margin: 0;
            padding: 0;
        }

        #audio_btn {
            width: 60px;
            height: 60px;
            background-image: url(../ima/muone.jpg);
            border-radius: 30px;
            background-size: contain;
            position: relative;
            opacity: 0.5;
            float: right;
        }

        .rotate {
            animation: rotating 2.5s linear infinite
        }

        @keyframes rotating {
            from {
                transform: rotate(0)
            }

            to {
                transform: rotate(360deg)
            }
        }

        .yinying {
            line-height: 200px;
            background: cadetblue;
            box-shadow: black 10px 20px 200px 5px;
            border-radius: 20px;
        }


        #myImg {
            border-radius: 5px;
            cursor: pointer;
            transition: 0.3s;
            border-radius:20px;
        }

        #dierzhang {
            border-radius: 5px;
            cursor: pointer;
            transition: 0.3s;
            border-radius:20px;
        }

         #disanzhang {
            border-radius: 5px;
            cursor: pointer;
            transition: 0.3s;
            border-radius:20px;
        }

            #myImg:hover {
                opacity: 0.7;
            }

        #dierzhang:hover {
            opacity: 0.7;
        }

        #disanzhang:hover {
            opacity: 0.7;
        }


        .modal {
            display: none;
            position: fixed;
            z-index: 1;
            padding-top: 100px;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            overflow: auto;
            background-color: rgb(0,0,0);
            background-color: rgba(0,0,0,0.9);
            position: fixed;
            overflow:hidden;
            opacity:0.92;
        }


        .modal-content {
            margin: auto;
            display: block;
            width: 80%;
            max-width: 80%;
            height:90%;
            max-height:90%;
            border-radius:20px;
        }


        #caption {
            margin: auto;
            display: block;
            width: 80%;
            max-width: 700px;
            text-align: center;
            color: #ccc;
            padding: 10px 0;
            height: 150px;
        }


        .modal-content, #caption {
            -webkit-animation-name: zoom;
            -webkit-animation-duration: 0.6s;
            animation-name: zoom;
            animation-duration: 0.6s;
        }

        @-webkit-keyframes zoom {
            from {
                -webkit-transform: scale(0)
            }

            to {
                -webkit-transform: scale(1)
            }
        }

        @keyframes zoom {
            from {
                transform: scale(0.1)
            }

            to {
                transform: scale(1)
            }
        }

        .close {
            position: absolute;
            top: 15px;
            right: 35px;
            color: #f1f1f1;
            font-size: 40px;
            font-weight: bold;
            transition: 0.3s;
        }

            .close:hover,
            .close:focus {
                color: #bbb;
                text-decoration: none;
                cursor: pointer;
            }


        @media only screen and (max-width: 700px) {
            .modal-content {
                width: 100%;
            }
        }
    </style>
    <script>
        var x = document.getElementById("media");
        $(function () {
            $("#audio_btn").click(function () {
                $(this).toggleClass("rotate");

                if ($(this).hasClass("rotate")) {
                    document.getElementById("media").play();
                } else {
                    document.getElementById("media").pause();
                }
            })
        });

        var c = document.getElementById("demo");
        var ctx = c.getContext("2d");
        ctx.shadowBlur = 10;
        ctx.shadowOffsetY = 20;
        ctx.shadowColor = "black";
        ctx.fillRect(20, 20, 100, 80);
    </script>

    <script>
        $(document).ready(function () {
            $("#myImg").click(function () {
            document.getElementById("myModal").style.display = "block";
                document.getElementById("img01").src = this.src;
                document.getElementById("img01").alt = this.alt;
            })
        });

                $(document).ready(function () {
            $("#dierzhang").click(function () {
            document.getElementById("myModal").style.display = "block";
                document.getElementById("img01").src = this.src;
                document.getElementById("img01").alt = this.alt;
                
            })
                });

                $(document).ready(function () {
            $("#disanzhang").click(function () {
            document.getElementById("myModal").style.display = "block";
                document.getElementById("img01").src = this.src;
                document.getElementById("img01").alt = this.alt;
                
            })
                });


        //modal.onclick = function () {

        //}

        // 获取 <span> 元素，设置关闭模态框按钮
        var span = document.getElementsByClassName("close")[0];

        // 点击 <span> 元素上的 (x), 关闭模态框
        $(document).ready(function () {
            $("#sppan").click(function () {
                document.getElementById("myModal").style.display = "none";
            })
        });

        //span.onclick = function () {
        //    modal.style.display = "none";
        //}
    </script>
    
</head>

<body style="overflow:hidden">

    <div id="myModal" class="modal">
        <!--这是遮罩层-->
        <span class="close" id="sppan">×</span>
        <img class="modal-content" id="img01" alt="">
        <div id="caption"></div>
    </div>

    <img src="../ima/backfour.jpg" style="width:100%;height:100%;top:0;bottom:0;left:0;right:0;position:fixed">
    <div id="audio_btn" class="rotate">
        <!--这是音乐-->
        <audio src="../ima/Ed Sheeran - Photograph.mp3" id="media" autoplay=""></audio>
    </div>
    <div class="snow-container" style="position:fixed;top:0;left:0;width:100%;height:100%;pointer-events:none;z-index:100001;"></div><!--这是动态-->
    <script type="text/javascript" src="all.js"></script>

    
    <div id="ccli" style="width:800px;height:1200px;margin:0 auto;text-align:center;align-items:center;display:flex;transform:scale(1,0.8)">

        <div id="demo" class="carousel slide yinying" data-ride="carousel">

            <!-- 指示符 -->
            <ul class="carousel-indicators">
                <li data-target="#demo" data-slide-to="0" class="active"></li>
                <li data-target="#demo" data-slide-to="1"></li>
                <li data-target="#demo" data-slide-to="2"></li>
            </ul>

            <!-- 轮播图片 -->
            <div class="carousel-inner">
                <div class="carousel-item active">
                    <img src="../ima/aa.jpg" id="myImg" alt="We get married">
                    <div class="carousel-caption">
                        <h3>We get married</h3>
                        <p>A handsome groom</p>
                    </div>
                </div>
                <div class="carousel-item">
                    <img src="../ima/bb.jpg" id="dierzhang" alt="put on shoes">
                    <div class="carousel-caption">
                        <h3>put on shoes</h3>
                        <p>Beautiful bride</p>
                    </div>
                </div>
                <div class="carousel-item">
                    <img src="../ima/cc.jpg"  id="disanzhang" alt="This is where we get married">
                    <div class="carousel-caption">
                        <h3>This is where we get married</h3>
                        <p>A beautiful place</p>
                    </div>
                </div>
            </div>

            <!-- 左右切换按钮 -->
            <a class="carousel-control-prev" href="#demo" data-slide="prev">
                <span class="carousel-control-prev-icon"></span>
            </a>
            <a class="carousel-control-next" href="#demo" data-slide="next">
                <span class="carousel-control-next-icon"></span>
            </a>

        </div>
    </div>
</body>
</html>
