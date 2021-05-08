function varargout = CitraRGBHistrogram(varargin)
% CITRARGBHISTROGRAM MATLAB code for CitraRGBHistrogram.fig
%      CITRARGBHISTROGRAM, by itself, creates a new CITRARGBHISTROGRAM or raises the existing
%      singleton*.
%
%      H = CITRARGBHISTROGRAM returns the handle to a new CITRARGBHISTROGRAM or the handle to
%      the existing singleton*.
%
%      CITRARGBHISTROGRAM('CALLBACK',hObject,eventData,handles,...) calls the local
%      function named CALLBACK in CITRARGBHISTROGRAM.M with the given input arguments.
%
%      CITRARGBHISTROGRAM('Property','Value',...) creates a new CITRARGBHISTROGRAM or raises the
%      existing singleton*.  Starting from the left, property value pairs are
%      applied to the GUI before CitraRGBHistrogram_OpeningFcn gets called.  An
%      unrecognized property name or invalid value makes property application
%      stop.  All inputs are passed to CitraRGBHistrogram_OpeningFcn via varargin.
%
%      *See GUI Options on GUIDE's Tools menu.  Choose "GUI allows only one
%      instance to run (singleton)".
%
% See also: GUIDE, GUIDATA, GUIHANDLES

% Edit the above text to modify the response to help CitraRGBHistrogram

% Last Modified by GUIDE v2.5 08-May-2021 03:24:36

% Begin initialization code - DO NOT EDIT
gui_Singleton = 1;
gui_State = struct('gui_Name',       mfilename, ...
                   'gui_Singleton',  gui_Singleton, ...
                   'gui_OpeningFcn', @CitraRGBHistrogram_OpeningFcn, ...
                   'gui_OutputFcn',  @CitraRGBHistrogram_OutputFcn, ...
                   'gui_LayoutFcn',  [] , ...
                   'gui_Callback',   []);
if nargin && ischar(varargin{1})
    gui_State.gui_Callback = str2func(varargin{1});
end

if nargout
    [varargout{1:nargout}] = gui_mainfcn(gui_State, varargin{:});
else
    gui_mainfcn(gui_State, varargin{:});
end
% End initialization code - DO NOT EDIT


% --- Executes just before CitraRGBHistrogram is made visible.
function CitraRGBHistrogram_OpeningFcn(hObject, eventdata, handles, varargin)
% This function has no output args, see OutputFcn.
% hObject    handle to figure
% eventdata  reserved - to be defined in a future version of MATLAB
% handles    structure with handles and user data (see GUIDATA)
% varargin   command line arguments to CitraRGBHistrogram (see VARARGIN)

% Choose default command line output for CitraRGBHistrogram
handles.output = hObject;

% Update handles structure
guidata(hObject, handles);

% UIWAIT makes CitraRGBHistrogram wait for user response (see UIRESUME)
% uiwait(handles.figure1);


% --- Outputs from this function are returned to the command line.
function varargout = CitraRGBHistrogram_OutputFcn(hObject, eventdata, handles) 
% varargout  cell array for returning output args (see VARARGOUT);
% hObject    handle to figure
% eventdata  reserved - to be defined in a future version of MATLAB
% handles    structure with handles and user data (see GUIDATA)

% Get default command line output from handles structure
varargout{1} = handles.output;


% --- Executes on button press in pushbutton1.
function pushbutton1_Callback(hObject, eventdata, handles)
% hObject    handle to pushbutton1 (see GCBO)
% eventdata  reserved - to be defined in a future version of MATLAB
% handles    structure with handles and user data (see GUIDATA)
[filename,pathname] = uigetfile({'*.*'});
 
if ~isequal(filename,0)
    Info = imfinfo(fullfile(pathname,filename));
    if Info.BitDepth == 24
        Img = imread(fullfile(pathname,filename));
        axes(handles.axes3)
        cla('reset')
        imshow(Img)
        title('Citra Asli')
    else
        msgbox('Citra masukan harus citra RGB');
        return
    end
else
    return
end
 
handles.Img = Img;
guidata(hObject,handles);
 
set(handles.radiobutton1,'Enable','on')
set(handles.radiobutton2,'Enable','on')
set(handles.radiobutton3,'Enable','on')
set(handles.radiobutton4,'Enable','on')
 
axes(handles.axes2)
cla('reset')
set(gca,'XTick',[])
set(gca,'YTick',[])
% --- Executes on button press in radiobutton1.
function radiobutton1_Callback(hObject, eventdata, handles)
% hObject    handle to radiobutton1 (see GCBO)
% eventdata  reserved - to be defined in a future version of MATLAB
% handles    structure with handles and user data (see GUIDATA)

% Hint: get(hObject,'Value') returns toggle state of radiobutton1
set(hObject,'Value',1)
set(handles.radiobutton1,'Value',0)
set(handles.radiobutton2,'Value',0)
set(handles.radiobutton3,'Value',0)
set(handles.radiobutton4,'Value',0)

Img = handles.Img;
axes(handles.axes1)
imshow(Img)
title('Citra RGB')
R = Img(:,:,1);
G = Img(:,:,2);
B = Img(:,:,3);

axes(handles.axes2)
cla('reset')
h = histogram(R(:));
h.FaceColor = [1 0 0];
xlim([0 255])
grid on
hold on
h = histogram(G(:));
h.FaceColor = [0 1 0];
xlim([0 255])
h = histogram(B(:));
h.FaceColor = [0 0 1];
xlim([0 255])
hold off
title('Histogram')

% --- Executes on button press in radiobutton2.
function radiobutton2_Callback(hObject, eventdata, handles)
% hObject    handle to radiobutton2 (see GCBO)
% eventdata  reserved - to be defined in a future version of MATLAB
% handles    structure with handles and user data (see GUIDATA)

% Hint: get(hObject,'Value') returns toggle state of radiobutton2
set(hObject,'Value',1)
set(handles.radiobutton1,'Value',0)
set(handles.radiobutton2,'Value',0)
set(handles.radiobutton3,'Value',0)
set(handles.radiobutton4,'Value',0)
 
Img = handles.Img;
R = Img(:,:,1);
G = Img(:,:,2);
B = Img(:,:,3);
Red_Channel = cat(3,R,G*0,B*0);
axes(handles.axes1)
cla('reset')
imshow(Red_Channel)
title('RED')
axes(handles.axes2)
cla('reset')
h = histogram(R(:));
h.FaceColor = [1 0 0];
xlim([0 255])
grid on
title('Histogram')

% --- Executes on button press in radiobutton3.
function radiobutton3_Callback(hObject, eventdata, handles)
% hObject    handle to radiobutton3 (see GCBO)
% eventdata  reserved - to be defined in a future version of MATLAB
% handles    structure with handles and user data (see GUIDATA)

% Hint: get(hObject,'Value') returns toggle state of radiobutton3
set(hObject,'Value',1)
set(handles.radiobutton1,'Value',0)
set(handles.radiobutton2,'Value',0)
set(handles.radiobutton3,'Value',0)
set(handles.radiobutton4,'Value',0)
 
Img = handles.Img;
R = Img(:,:,1);
G = Img(:,:,2);
B = Img(:,:,3);
Green_Channel = cat(3,R*0,G,B*0);
axes(handles.axes1)
cla('reset')
imshow(Green_Channel)
title('GREEN')
axes(handles.axes2)
cla('reset')
h = histogram(G(:));
h.FaceColor = [0 1 0];
xlim([0 255])
grid on
title('Histogram')

% --- Executes on button press in radiobutton4.
function radiobutton4_Callback(hObject, eventdata, handles)
% hObject    handle to radiobutton4 (see GCBO)
% eventdata  reserved - to be defined in a future version of MATLAB
% handles    structure with handles and user data (see GUIDATA)

% Hint: get(hObject,'Value') returns toggle state of radiobutton4
set(hObject,'Value',1)
set(handles.radiobutton1,'Value',0)
set(handles.radiobutton2,'Value',0)
set(handles.radiobutton3,'Value',0)
set(handles.radiobutton4,'Value',0)

Img = handles.Img;
R = Img(:,:,1);
G = Img(:,:,2);
B = Img(:,:,3);
Blue_Channel = cat(3,R*0,G*0,B);
axes(handles.axes1)
cla('reset')
imshow(Blue_Channel)
title('BLUE')
axes(handles.axes2)
cla('reset')
h = histogram(B(:));
h.FaceColor = [0 0 1];
xlim([0 255])
grid on
title('Histogram')


% --- Executes on button press in radiobutton7.
function radiobutton7_Callback(hObject, eventdata, handles)
% hObject    handle to radiobutton7 (see GCBO)
% eventdata  reserved - to be defined in a future version of MATLAB
% handles    structure with handles and user data (see GUIDATA)

% Hint: get(hObject,'Value') returns toggle state of radiobutton7
set(hObject,'Value',1)
set(handles.radiobutton1,'Value',0)
set(handles.radiobutton2,'Value',0)
set(handles.radiobutton3,'Value',0)
set(handles.radiobutton4,'Value',0)
set(handles.radiobutton7,'Value',0)
set(handles.radiobutton8,'Value',0)



Img = handles.Img;
Gray = rgb2gray(Img);
I_adjust = imadjust(Gray,[40/255 204/255],[0/255 255/255]);

axes(handles.axes3)
cla('reset')
imshow(Gray)
title('Citra Asli')
ax = gca;
ax.FontSize = 8;

axes(handles.axes1)
cla('reset')
imshow(I_adjust)
title('Hasil Penambahan Contras')
ax = gca;
ax.FontSize = 8;

axes(handles.axes2)
h = histogram(I_adjust(:));
h.FaceColor = [0.5 0.5 0.5];
xlim([0 255])
grid on
title('Histogram Hasil Penambahan')
ax = gca;
ax.FontSize = 8;


% --- Executes on button press in radiobutton8.
function radiobutton8_Callback(hObject, eventdata, handles)
% hObject    handle to radiobutton8 (see GCBO)
% eventdata  reserved - to be defined in a future version of MATLAB
% handles    structure with handles and user data (see GUIDATA)

% Hint: get(hObject,'Value') returns toggle state of radiobutton8
set(hObject,'Value',1)
set(handles.radiobutton1,'Value',0)
set(handles.radiobutton2,'Value',0)
set(handles.radiobutton3,'Value',0)
set(handles.radiobutton4,'Value',0)
set(handles.radiobutton7,'Value',0)
set(handles.radiobutton8,'Value',0)


Img = handles.Img;
Gray = rgb2gray(Img);
I_adjust = imadjust(Gray,[0 0.2],[0.5 1]);

axes(handles.axes3)
cla('reset')
imshow(Gray)
title('Citra Asli')
ax = gca;
ax.FontSize = 8;

axes(handles.axes1)
cla('reset')
imshow(I_adjust)
title('Hasil Penurunan Contras')
ax = gca;
ax.FontSize = 8;

axes(handles.axes2)
h = histogram(I_adjust(:));
h.FaceColor = [0.5 0.5 0.5];
xlim([0 255])
grid on
title('Histogram Hasil Penurunan')
ax = gca;
ax.FontSize = 8;
